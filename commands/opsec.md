---
label: Security
icon: shield-lock
order: 990
---

# Security

Configure Drew's protection modules: anti-nuke, anti-raid, punishments, thresholds, whitelists and presets.

!!!info Who can use it
By default, members with **Manage Server**. Server admins can change this in Server Settings, Integrations.
!!!

- Every subcommand except `config` and `servershow` requires an active SUDO session. Run `/sudo enter` first.
- Features that take effect today: `nuke` (anti-nuke) and `raid` (anti-raid). `links` and `invites` are stored for an upcoming module and have no effect yet.
- Punishments and limits that take effect today: `nuke`, `raid`, `channel_delete`, `channel_create`, `role_delete`, `role_create` and `join_rate`. Other values are accepted and stored for upcoming modules.

## /opsec config

View current security settings.

| Option | Type | Required | Description |
|---|---|---|---|
| `category` | Text | Yes | Choose the settings category. Values: `anti_nuke`, `verification`, `beast_mode`, `whitelist`, `backup`. |

## /opsec snapshot

Manage server security snapshots.

| Option | Type | Required | Description |
|---|---|---|---|
| `action` | Text | Yes | Action to perform. Values: `save`, `load`, `delete`. |

## /opsec enable

Enable a protection feature.

Values for `feature`: `nuke`, `raid`, `links`, `invites`.

| Option | Type | Required | Description |
|---|---|---|---|
| `feature` | Text | Yes | Feature to enable |

## /opsec disable

Disable a protection feature (Requires SUDO).

Values for `feature`: `nuke`, `raid`, `links`, `invites`.

| Option | Type | Required | Description |
|---|---|---|---|
| `feature` | Text | Yes | Feature to disable |

## /opsec punishment

Configure punishment for an action.

Values for `action`: `nuke`, `raid`, `channel_delete`, `channel_create`, `role_delete`, `role_create`, `dangerous_permissions`, `admin_role`, `invite_link`, `spam`, `antibot`.

| Option | Type | Required | Description |
|---|---|---|---|
| `action` | Text | Yes | The action to punish |
| `type` | Text | Yes | Punishment type. Values: `none`, `timeout`, `kick`, `ban`. |

## /opsec limit

Configure threshold for an action.

Values for `action`: `ban`, `kick`, `channel_delete`, `channel_create`, `role_delete`, `role_create`, `join_rate`. Limits count actions by one user within 10 seconds (`join_rate` counts joins).

| Option | Type | Required | Description |
|---|---|---|---|
| `action` | Text | Yes | The action to limit |
| `threshold` | Integer | Yes | Threshold value |

## /opsec whitelist

Manage security whitelists.

| Option | Type | Required | Description |
|---|---|---|---|
| `action` | Text | Yes | Add/Remove from whitelist. Values: `add_user`, `remove_user`, `add_role`, `remove_role`. |
| `user` | User | No | The user to whitelist |
| `role` | Role | No | The role to whitelist |

## /opsec setup

Apply a security preset.

Presets turn anti-nuke and anti-raid on (or off with `unprotected`) and set the join-rate thresholds: `basic` 6 joins in 30 s, `guarded` 5 in 25 s, `fortress` 4 in 20 s.

| Option | Type | Required | Description |
|---|---|---|---|
| `tier` | Text | Yes | Preset tier to apply. Values: `basic`, `guarded`, `fortress`, `unprotected`. |

## /opsec servershow

Show or hide this server in the carousel on drewbot.xyz.

`off` hides this server from the carousel on drewbot.xyz, `on` shows it again. Servers are shown by default. Doesn't need SUDO.

| Option | Type | Required | Description |
|---|---|---|---|
| `state` | Text | Yes | on shows the server, off hides it. Values: `on`, `off`. |
