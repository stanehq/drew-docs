---
label: FAQ
icon: question
order: 100
---

# Frequently asked questions

## Setup and access

### Who can configure Drew?

- `/opsec` needs **Manage Server** and, for every change, an active **SUDO** session.
- `/sudo setup` (the SUDO password) is **server owner** only.
- On the [dashboard](https://drewbot.xyz/dashboard), only the server owner can save changes. Admins and managers can view.
- With the [API](../api.md), a token can only change what its scope allows, and only in its own server.

### Can a rogue admin turn Drew off?

Not without the SUDO password. Disabling protections, changing limits or whitelists and banning or kicking through Drew all need `/sudo enter`. Keep the password with the owner only.

### What if the owner account is compromised?

Drew always trusts the server owner, so protect that account: enable two-factor authentication and never scan QR codes or log in through links from strangers. If it happens, contact [Discord support](https://support.discord.com) and our [support server](https://discord.gg/5e2jm7QDSS).

### Does Drew use a prefix?

No. Every command is a slash command. Type `/` to see them.

## Protection

### How does Drew decide that something is a nuke?

It counts destructive actions per user from the audit log: channel and role creations and deletions. When one user passes the limit (5 in 10 seconds by default), Drew applies your punishment. See [Anti-nuke](../features/antinuke.md).

### How does it detect raids?

It counts joins in a time window. Past your limit, members who join are punished. See [Anti-raid](../features/antiraid.md).

### Why didn't Drew punish someone?

Most often the punishment is still `none`, the user is whitelisted, or their role is above Drew's. See [Troubleshooting](troubleshooting.md).

### Why did Drew punish one of my bots?

It created or deleted channels or roles fast enough to look like a nuke. If you trust it, whitelist it with `/opsec whitelist action:add_user`.

### Does Drew protect webhooks, emojis, bans or the vanity URL?

Not yet. These are on the [Roadmap](../features/roadmap.md).

### Can Drew restore channels after a nuke?

Not yet. Automatic recovery is on the [Roadmap](../features/roadmap.md). Today Drew stops the attacker early, which limits the damage. Use [Backups](../features/backups.md) to save your configuration.

## Permissions

### Why does Drew need Administrator?

To act in every channel and on every member it may need to punish, without breaking when you add new channels or overrides.

### Why can't Drew moderate a member?

Their highest role is at or above Drew's. Move Drew's role higher in **Server Settings, Roles**.

## Privacy and safety

### What data does Drew keep?

See the [Privacy Policy](https://drewbot.xyz/privacy).

### Can I hide my server from drewbot.xyz?

Yes. The home page shows the largest servers using Drew (name, icon and number of people). To hide yours, run `/opsec servershow state:off`, or turn off **Show on drewbot.xyz** on the dashboard. It also works through the API with the `showcase_enabled` setting.

### Is this bot really Drew?

The official Drew bot is invited from [drewbot.xyz](https://drewbot.xyz) and its application ID is `1441457111409103010`. Drew will never ask for your password, your Discord token or to scan a QR code. If another bot claims to be Drew, remove it and report it to Discord and to our [support server](https://discord.gg/5e2jm7QDSS).
