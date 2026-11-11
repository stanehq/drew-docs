---
label: Anti-raid
icon: people
order: 90
---

# Anti-raid

Anti-raid detects join floods. When more members join than your limit allows in a time window, Drew punishes the members who join during the raid.

## How it works

- **Join limit**: number of joins that counts as a raid (`join_rate_limit`).
- **Window**: length of the window in seconds (`join_window_seconds`).
- **Punishment**: `none`, `timeout` (15 minutes), `kick` or `ban` (`raid_punishment`).

A join limit of `0` turns detection off.

## Presets

`/opsec setup` applies tested values in one step:

| Preset | Raid threshold |
|---|---|
| `basic` | 6 joins in 30 seconds |
| `guarded` | 5 joins in 25 seconds |
| `fortress` | 4 joins in 20 seconds |
| `unprotected` | Turns anti-nuke and anti-raid off |

Presets don't change your punishments. Set one with `/opsec punishment action:raid`.

## Set it up

1. `/sudo enter`
2. `/opsec setup tier:guarded`
3. `/opsec punishment action:raid type:kick`

!!!tip
Large events (giveaways, partnerships) can bring real join spikes. Raise the limit for the day instead of turning anti-raid off.
!!!
