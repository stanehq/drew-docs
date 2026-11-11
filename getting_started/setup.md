---
label: Setup
icon: gear
order: 80
---

# Setup

This takes about two minutes. Run the commands in a private staff channel.

## 1. Set the SUDO password (owner)

```
/sudo setup password:<a strong password>
```

Sensitive commands now need `/sudo enter` first. See [SUDO mode](../features/sudo.md).

## 2. Turn on protection

```
/sudo enter password:<your password>
/opsec setup tier:guarded
/opsec punishment action:nuke type:ban
/opsec punishment action:raid type:kick
```

`guarded` turns on anti-nuke and anti-raid with balanced limits. The punishments matter: the default is `none`, which only detects. See [Anti-nuke](../features/antinuke.md) and [Anti-raid](../features/antiraid.md).

## 3. Trust your other bots

Other bots that create or delete channels or roles (ticket bots, for example) should be whitelisted so anti-nuke doesn't punish them:

```
/opsec whitelist
```

## 4. Turn on logs

```
/log set channel:#logs
```

## 5. Optional

- Verification: `/verify setup` then `/verify send`. See [Verification](../features/verification.md).
- Back up the result: `/bkp save`.

## Check your setup

`/opsec config category:anti_nuke` shows what is active. You can also review everything on the [dashboard](https://drewbot.xyz/dashboard).
