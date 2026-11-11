---
label: Moderation
icon: stop
order: 970
---

# Moderation

Day-to-day moderation: bans, kicks, timeouts, warnings, purges, channel locks and case history.

- `ban`, `kick`, `unban`, `lockall` and `unlockall` also require an active SUDO session.

## /mod ban

Ban a member from the server.

Requires an active SUDO session (`/sudo enter`).

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to ban |
| `reason` | Text | No | Reason for the ban |

## /mod kick

Kick a member from the server.

Requires an active SUDO session (`/sudo enter`).

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to kick |
| `reason` | Text | No | Reason for the kick |

## /mod timeout

Timeout a member in minutes.

Requires Moderate Members.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to timeout |
| `minutes` | Integer | Yes | Duration in minutes |
| `reason` | Text | No | Reason for the timeout |

## /mod untimeout

Remove a timeout from a member.

Requires Moderate Members.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to untimeout |
| `reason` | Text | No | Reason |

## /mod purge

Delete a number of messages in the channel.

Requires Manage Messages.

| Option | Type | Required | Description |
|---|---|---|---|
| `amount` | Integer | Yes | Number of messages to delete |
| `user` | User | No | Only delete messages from this user |

## /mod unban

Unban a user from the server.

Requires an active SUDO session (`/sudo enter`).

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to unban |
| `reason` | Text | No | Reason |

## /mod lock

Lock the current channel.

Requires Manage Channels.

## /mod unlock

Unlock the current channel.

Requires Manage Channels.

## /mod slowmode

Set the slowmode for the channel.

Requires Manage Channels.

| Option | Type | Required | Description |
|---|---|---|---|
| `seconds` | Integer | Yes | Slowmode in seconds (0 to disable) |

## /mod warn

Warn a member.

Requires Kick Members.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to warn |
| `reason` | Text | Yes | Reason for the warning |

## /mod sanitize

Clean a member's nickname.

Requires Manage Nicknames.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | User to sanitize |

## /mod lockall

Lock all text channels.

Requires an active SUDO session (`/sudo enter`).

## /mod unlockall

Unlock all text channels.

Requires an active SUDO session (`/sudo enter`).

## /mod cases

View or modify moderation cases.

Requires Manage Server or Administrator.

| Option | Type | Required | Description |
|---|---|---|---|
| `operation` | Text | Yes | Select an action. Values: `view`, `modify`. |
| `user` | User | No | Filter cases by user (view) |
| `case_id` | Integer | No | Case ID to edit (modify) |
| `reason` | Text | No | New reason (modify) |
