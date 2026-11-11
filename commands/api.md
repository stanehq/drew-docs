---
label: API tokens
icon: key-asterisk
order: 930
---

# API tokens

Create and manage tokens for the [Configuration API](../developers/api/intro.md).

!!!info Who can use it
By default, members with **Administrator**. Server admins can change this in Server Settings, Integrations.
!!!

- Creating a token requires being the server owner or having an active SUDO session. `admin` tokens can only be created by the owner.
- The token is shown once, only to you. Drew stores only its SHA-256 hash.

## /api token create

Create an API token (requires server owner or an active SUDO session).

| Option | Type | Required | Description |
|---|---|---|---|
| `name` | Text | Yes | What the token is for, e.g. "claude-setup" |
| `scope` | Text | Yes | What the token can do. Values: `read`, `write`, `admin`. |
| `expires` | Text | No | When the token stops working (default: 30 days). Values: `1`, `7`, `30`, `90`, `365`. |

## /api token list

List this server's active API tokens.

## /api token revoke

Revoke an API token immediately.

Requires the server owner or an active SUDO session.

| Option | Type | Required | Description |
|---|---|---|---|
| `token` | Text | Yes | Token prefix (drew_xxxxxxxx) or ID from /api token list |

## /api docs

How to configure Drew through the API.
