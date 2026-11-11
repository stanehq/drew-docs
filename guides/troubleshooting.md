---
label: Troubleshooting
icon: tools
order: 90
---

# Troubleshooting

## Drew doesn't answer commands

1. Check the [status page](https://drewbot.xyz/status). If there is an incident, wait for it to clear.
2. Try `/gen ping` in another channel. If it works there, the first channel blocks Drew: check its overrides and those of its category.
3. Make sure Drew is still in the server and still has **Administrator**.

## "This action requires an active SUDO session"

Run `/sudo enter` and try again. Sessions last 15 minutes. If no password exists yet, the server owner sets one with `/sudo setup`. See [SUDO mode](../features/sudo.md).

## Anti-nuke or anti-raid detected something but did nothing

Check these in order:

1. **Punishment**: the default is `none`. Set one with `/opsec punishment`.
2. **Enabled**: `/opsec config category:anti_nuke` shows whether it is on.
3. **Whitelist**: the user, or one of their roles, may be whitelisted. The server owner is always trusted.
4. **Role position**: Drew can't act on members whose highest role is at or above Drew's role. Move Drew's role up.
5. **Limits**: the action may not have reached the limit (5 in 10 seconds by default, per user).

## A legitimate bot was punished

Bots that create or delete channels or roles (ticket bots, for example) look like nukes. Whitelist them with `/opsec whitelist action:add_user`. Whitelist only bots you trust: a whitelisted account can't be stopped by anti-nuke.

## Verification doesn't give the role

Drew's role must be above the verification role. Also check that the role in `/verify setup` still exists.

## Logs don't appear

Run `/log status`. Make sure the log channel still exists, Drew can send messages there, and the category is turned on (`/log toggle`).

## Still stuck?

Ask in our [support server](https://discord.gg/5e2jm7QDSS). Include the server ID, the exact command, the error message and roughly when it happened (with your time zone).

:::danger
Never share your SUDO password, API tokens or any other secret, not even with staff.
:::
