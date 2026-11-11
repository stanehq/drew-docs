---
label: Logging
icon: note
order: 960
---

# Logging

Send server events to a log channel: messages, members, moderation, channels, roles, voice, invites and server changes.

- Every configuration change made with commands, the dashboard or the API is also announced in the log channel.

## /log set

Set the audit log channel.

| Option | Type | Required | Description |
|---|---|---|---|
| `channel` | Channel | Yes | Channel for audit logs |
| `debounce` | Integer | No | Seconds between duplicate logs |

## /log toggle

Enable/disable specific log categories.

| Option | Type | Required | Description |
|---|---|---|---|
| `category` | Text | Yes | The category to toggle. Values: `message`, `member`, `moderation`, `channel`, `role`, `voice`, `invite`, `guild`. |

## /log status

Show logging status and enabled categories.

## /log clear

Clear the audit log channel.
