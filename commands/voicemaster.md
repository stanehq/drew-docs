---
label: VoiceMaster
icon: unmute
order: 880
---

# VoiceMaster

Join to Create voice rooms that members can manage themselves.

## /setup default

Create default Join to Create channel.

| Option | Type | Required | Description |
|---|---|---|---|
| `channel` | Channel | Yes | Voice channel |

## /setup predefined

Channels with variable names.

## /set channel

Set Join to Create channel.

| Option | Type | Required | Description |
|---|---|---|---|
| `channel` | Channel | Yes | The channel |

## /set role

Set moderator role.

| Option | Type | Required | Description |
|---|---|---|---|
| `role` | Role | Yes | The role |

## /set bitrate

Set default bitrate.

| Option | Type | Required | Description |
|---|---|---|---|
| `bitrate` | Integer | Yes | 8-384 |

## /toggle list

Show all toggles.

## /toggle set

Set a toggle.

| Option | Type | Required | Description |
|---|---|---|---|
| `feature` | Text | Yes | Feature name |
| `state` | True/False | Yes | On/Off |

## /voice lock

Lock room.

## /voice unlock

Unlock room.

## /voice ghost

Hide room.

## /voice unghost

Unhide room.

## /voice claim

Claim room.

## /voice limit

Set limit.

| Option | Type | Required | Description |
|---|---|---|---|
| `limit` | Integer | Yes | Count |

## /voice name

Rename room.

| Option | Type | Required | Description |
|---|---|---|---|
| `name` | Text | Yes | New name |

## /voice game

Rename to activity.

## /voice bitrate

Set bitrate.

| Option | Type | Required | Description |
|---|---|---|---|
| `kbps` | Integer | Yes | Bitrate |

## /voice permit

Permit user.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | Target |

## /voice reject

Reject user.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | Target |

## /voice status

Set room status.

| Option | Type | Required | Description |
|---|---|---|---|
| `text` | Text | Yes | The status |

## /voice region

Set voice region.

| Option | Type | Required | Description |
|---|---|---|---|
| `region` | Text | Yes | The region. Values: `us-east`, `us-west`, `rotterdam`, `brazil`, `hongkong`. |

## /voice transfer

Transfer ownership.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | Yes | New owner |

## /voice text

Toggle private text channel.

## /interface

Control panel.
