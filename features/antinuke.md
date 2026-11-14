---
label: Anti-nuke
icon: shield-check
order: 100
---

# Anti-nuke

Anti-nuke stops a compromised or malicious account from wiping your server. Drew watches the audit log and punishes anyone who creates or deletes too many channels or roles in a short time.

## What it watches

| Action | Default limit |
|---|---|
| Channel deletions | 5 in 10 seconds |
| Channel creations | 5 in 10 seconds |
| Role deletions | 5 in 10 seconds |
| Role creations | 5 in 10 seconds |

Limits count actions by **one user**, so a user is never punished for something another member did.

## Punishments

Each action can use `none`, `timeout` (15 minutes), `kick` or `ban`. An action set to `none` falls back to the general anti-nuke punishment.

!!!warning Set a punishment
The default punishment is `none`. Until you set one, Drew detects nukes but takes no action. Run `/opsec punishment` with action `nuke` and type `ban`.
!!!

## Who is never punished

- The server owner and Drew itself.
- Users and roles on the anti-nuke whitelist (`/opsec whitelist`).

Keep the whitelist short. Every trusted account is an account that can nuke your server if it is compromised.

## Set it up

1. Enter SUDO mode: `/sudo enter`.
2. Turn it on: `/opsec enable feature:nuke`.
3. Choose a punishment: `/opsec punishment action:nuke type:ban`.
4. Optional: change the limits with `/opsec limit`, for example `action:channel_delete threshold:3`.
5. Trust your other bots: `/opsec whitelist`.

You can also configure all of this from the [dashboard](https://drewbot.xyz/dashboard) or the [Configuration API](../api.md).

## Requirements

Drew needs to see the audit log and its role must be **above** the roles of anyone it may punish. See [Permissions](../getting_started/permissions.md).
