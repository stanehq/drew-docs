---
label: General
icon: info
order: 900
---

# General

Help, bot info, server and user info, feedback, reports and message snipes.

## /gen help

Show help menu.

## /gen about

Show bot info.

## /gen ping

Show latency.

## /gen dashboard

Manage everything.

## /gen invite

Invite link.

## /gen infouser

Show user info.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | No | Target |

## /gen infoserver

Show server info.

## /gen feedback

Send feedback.

| Option | Type | Required | Description |
|---|---|---|---|
| `content` | Text | Yes | Your feedback |

## /gen report

Report a user.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | Target |
| `reason` | Text | Yes | Reason for report |

## /gen snipe

Snipe latest deleted message.

| Option | Type | Required | Description |
|---|---|---|---|
| `index` | Integer | No | Message index |

## /gen editsnipe

Snipe latest edited message.

| Option | Type | Required | Description |
|---|---|---|---|
| `index` | Integer | No | Edit index |

## /gen reactionsnipe

Snipe latest removed reaction.

## /gen clearsnipe

Clear all snipes (Manage Messages req).

Requires Manage Messages.

## /gen reactionhistory

View reaction history for message.

Requires Manage Messages.

| Option | Type | Required | Description |
|---|---|---|---|
| `messagelink` | Text | Yes | Discord message link |
