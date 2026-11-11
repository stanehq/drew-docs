---
label: Giveaways
icon: gift
order: 920
---

# Giveaways

Run giveaways with a timer, winners and an optional required role.

!!!info Who can use it
By default, members with **Manage Server**. Server admins can change this in Server Settings, Integrations.
!!!

## /giveaway start

Launch a new giveaway.

| Option | Type | Required | Description |
|---|---|---|---|
| `title` | Text | Yes | Prize or giveaway title |
| `duration` | Text | Yes | Duration (e.g. 10m, 2h, 1d) |
| `winners` | Integer | Yes | Number of winners |
| `required_role` | Role | No | Role required to enter (optional) |

## /giveaway end

Force-end an active giveaway.

| Option | Type | Required | Description |
|---|---|---|---|
| `message_id` | Text | Yes | Giveaway message ID |

## /giveaway reroll

Reroll a winner for an ended giveaway.

| Option | Type | Required | Description |
|---|---|---|---|
| `message_id` | Text | Yes | Giveaway message ID |

## /giveaway list

List all active giveaways in this server.

## /giveaway pause

Pause an active giveaway (timer stops).

| Option | Type | Required | Description |
|---|---|---|---|
| `message_id` | Text | Yes | Giveaway message ID |

## /giveaway resume

Resume a paused giveaway.

| Option | Type | Required | Description |
|---|---|---|---|
| `message_id` | Text | Yes | Giveaway message ID |

## /giveaway delete

Delete a giveaway permanently.

| Option | Type | Required | Description |
|---|---|---|---|
| `message_id` | Text | Yes | Giveaway message ID |
