---
label: SUDO mode
icon: lock
order: 60
---

# SUDO mode

Sensitive actions need a password that only the server owner sets. If an admin account is compromised, the attacker still can't switch your protection off.

## What needs SUDO

- Every `/opsec` subcommand except `config`.
- `/mod ban`, `/mod kick`, `/mod unban`, `/mod lockall` and `/mod unlockall`.
- Creating API tokens (unless you are the owner) and revoking them.

## Use it

1. The owner sets the password once: `/sudo setup`.
2. Admins start a 15-minute session with `/sudo enter`.
3. `/sudo status` shows the time left and `/sudo exit` ends it early.

Never share the SUDO password in a channel. Change it with `/sudo setup` if you think it leaked.
