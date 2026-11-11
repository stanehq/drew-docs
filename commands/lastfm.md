---
label: Last.fm
icon: broadcast
order: 870
---

# Last.fm

Show what you're listening to and your Last.fm stats.

## /lastfm set

Set your Last.fm username.

| Option | Type | Required | Description |
|---|---|---|---|
| `username` | Text | Yes | Your Last.fm username |

## /lastfm np

Show what you are currently playing.

| Option | Type | Required | Description |
|---|---|---|---|
| `user` | User | No | User to check (defaults to you) |

## /lastfm stats

Show your Last.fm stats.

## /lastfm milestone

How many scrobbles until a milestone.

| Option | Type | Required | Description |
|---|---|---|---|
| `number` | Integer | Yes | The milestone number (e.g. 10000) |

## /lastfm playsalbum

Check how many plays you have for an album.

| Option | Type | Required | Description |
|---|---|---|---|
| `query` | Text | Yes | Artist - Album name |
| `member` | User | No | Member to check (defaults to you) |
