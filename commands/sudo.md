---
label: SUDO
icon: key
order: 980
---

# SUDO

SUDO mode protects sensitive changes with a password that only the server owner sets, so a compromised admin account can't switch your protection off.

- Sessions last 15 minutes. Use `/sudo exit` to end one early.

## /sudo enter

Enter SUDO mode for 15 minutes.

Requires the Administrator permission.

| Option | Type | Required | Description |
|---|---|---|---|
| `password` | Text | No | Required after the server owner configures SUDO |

## /sudo exit

Exit SUDO mode immediately.

## /sudo status

Check current SUDO session status.

## /sudo setup

Configure SUDO protection (Owner only).

Server owner only.

| Option | Type | Required | Description |
|---|---|---|---|
| `password` | Text | Yes | Set or update the SUDO password |
