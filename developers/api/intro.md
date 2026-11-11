---
label: Configuration API
icon: graph
order: 100
---

# Configuration API

Configure Drew from scripts, CI or AI agents without opening a dashboard. The
website's dashboard uses these same endpoints, with the same validation.

!!!success Base URL
`https://api.drewbot.xyz/api/v1`
!!!

## 1. Get a token

In your server, as an administrator:

```
/api token create name:<what it's for> scope:<read|write|admin> expires:<1-365 days>
```

- Creating a token requires being the **server owner** or having an active
  **SUDO** session (`/sudo enter`).
- `admin` tokens can only be created by the server owner.
- The token is shown **once**, only to you. Drew stores only its SHA-256 hash.
- A server can have at most 10 active tokens. List them with `/api token list`
  and revoke one instantly with `/api token revoke <prefix>`.

| Scope | Allows |
|---|---|
| `read` | Guild info, channels, roles, settings, audit log |
| `write` | `read` + changing non-privileged settings |
| `admin` | `write` + privileged settings (anti-nuke whitelists) |

Send it on every request:

```
Authorization: Bearer drew_…
```

A token only works for the server it was created in.

## 2. Discover the settings

```
GET /schema
```

Public, no token needed. Returns every setting with its `type`, `options`,
`min`/`max`, `default`, `description`, `category`, whether the bot currently
enforces it (`enforced`), and whether it is `privileged`. Read the schema
before changing settings: it is the source of truth.

Value types:

| Type | JSON value |
|---|---|
| `boolean` | `true` / `false` |
| `integer` | number between `min` and `max` |
| `enum` | one of `options` |
| `channel_id` | text channel ID **string** in the same server, or `null` |
| `role_id` | role ID **string** in the same server, or `null` |
| `user_id_list` / `role_id_list` | array of ID strings |
| `string_set` | array of `options`, or `["all"]` |

Discord IDs are always strings (they do not fit in a JavaScript number).

## 3. Endpoints

| Method | Path | Scope | Description |
|---|---|---|---|
| GET | `/schema` | none | All configurable settings |
| GET | `/me` | read | Which server and scope this token has |
| GET | `/guilds/{guild_id}` | read | Name, icon, member count, owner |
| GET | `/guilds/{guild_id}/channels` | read | Text channels (to pick `channel_id` values) |
| GET | `/guilds/{guild_id}/roles` | read | Assignable roles (to pick `role_id` values) |
| GET | `/guilds/{guild_id}/settings` | read | Current settings |
| PATCH | `/guilds/{guild_id}/settings` | write | Change settings |
| GET | `/guilds/{guild_id}/audit?limit=50` | read | Recent changes and who made them |

### Changing settings

```http
PATCH /guilds/123456789012345678/settings
Authorization: Bearer drew_…
Content-Type: application/json

{
  "settings": {
    "anti_nuke_enabled": true,
    "nuke_punishment": "ban",
    "channel_delete_limit": 3,
    "log_channel_id": "234567890123456789"
  },
  "dry_run": true
}
```

- **Atomic:** if any field is invalid, nothing is changed and the response
  lists every problem in `error.fields`.
- **`dry_run: true`** validates and returns the `changes` that would be made
  (`{"key": {"old": …, "new": …}}`) without applying them. Use it first.
- Only changed fields are written. Every applied change is stored in the audit
  log and announced in the server's log channel, if one is configured.

Response:

```json
{
  "guild_id": "123456789012345678",
  "dry_run": false,
  "applied": true,
  "changes": { "nuke_punishment": { "old": "none", "new": "ban" } },
  "settings": { "...": "full settings after the change" }
}
```

## 4. Errors

All errors look like:

```json
{ "error": { "code": "INVALID_SETTINGS", "message": "…", "fields": [{ "key": "…", "message": "…" }] } }
```

| Status | Code | Meaning |
|---|---|---|
| 401 | `UNAUTHORIZED` / `INVALID_TOKEN` | Missing, invalid, expired or revoked token |
| 403 | `INSUFFICIENT_SCOPE` / `WRONG_GUILD` | Token lacks the scope or belongs to another server |
| 403 | `INVALID_SETTINGS` | A privileged setting needs an `admin` token |
| 404 | `GUILD_NOT_FOUND` | Drew is not in that server |
| 409 | `BUSY` | Another change is in progress; retry |
| 422 | `INVALID_BODY` / `INVALID_SETTINGS` | Malformed body or invalid values |
| 429 | `RATE_LIMITED` | Slow down |

## 5. Limits

- 100 requests per minute per IP.
- 120 reads and 30 setting changes per minute per token.
- At most 100 settings per PATCH.

## 6. Guidance for AI agents

1. `GET /me` to learn the server ID and scope.
2. `GET /schema`, then `GET /guilds/{id}/settings`, `/channels` and `/roles`.
3. Prefer settings with `enforced: true`; the others are stored but have no
   effect yet.
4. Send the change with `dry_run: true`, show the `changes` to the human, and
   only then send it again with `dry_run: false`.
5. Never print the token. If it leaks, ask the owner to run `/api token revoke`.

!!!warning Keep tokens secret
A token can change your server's security settings. Never paste it in a public channel, a repository or a screenshot.
!!!

## Security model

- Tokens are random 256-bit secrets, stored hashed, scoped to one server,
  time-limited and revocable.
- Channel and role references are checked against the server, so a setting
  can never point at another server; `@everyone` and bot-managed roles cannot
  be whitelisted.
- The SUDO password and internal fields (premium, owner) are never readable or
  writable through the API.
- Every change is attributed (`token:drew_xxxxxxxx`, or `user:<id>` for the
  dashboard) in the audit log and in the server's log channel.
