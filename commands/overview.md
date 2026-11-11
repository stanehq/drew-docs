---
label: Overview
icon: list-unordered
order: 2000
---

# Commands

Every Drew command is a slash command. Type `/` in Discord to see them with autocomplete. This page lists them all. Open a category for options and permissions.


## [Security](opsec.md)

| Command | Description |
|---|---|
| `/opsec config` | View current security settings |
| `/opsec snapshot` | Manage server security snapshots |
| `/opsec enable` | Enable a protection feature |
| `/opsec disable` | Disable a protection feature (Requires SUDO) |
| `/opsec punishment` | Configure punishment for an action |
| `/opsec limit` | Configure threshold for an action |
| `/opsec whitelist` | Manage security whitelists |
| `/opsec setup` | Apply a security preset |

## [SUDO](sudo.md)

| Command | Description |
|---|---|
| `/sudo enter` | Enter SUDO mode for 15 minutes |
| `/sudo exit` | Exit SUDO mode immediately |
| `/sudo status` | Check current SUDO session status |
| `/sudo setup` | Configure SUDO protection (Owner only) |

## [Moderation](mod.md)

| Command | Description |
|---|---|
| `/mod ban` | Ban a member from the server |
| `/mod kick` | Kick a member from the server |
| `/mod timeout` | Timeout a member in minutes |
| `/mod untimeout` | Remove a timeout from a member |
| `/mod purge` | Delete a number of messages in the channel |
| `/mod unban` | Unban a user from the server |
| `/mod lock` | Lock the current channel |
| `/mod unlock` | Unlock the current channel |
| `/mod slowmode` | Set the slowmode for the channel |
| `/mod warn` | Warn a member |
| `/mod sanitize` | Clean a member's nickname |
| `/mod lockall` | Lock all text channels |
| `/mod unlockall` | Unlock all text channels |
| `/mod cases` | View or modify moderation cases |

## [Logging](log.md)

| Command | Description |
|---|---|
| `/log set` | Set the audit log channel |
| `/log toggle` | Enable/disable specific log categories |
| `/log status` | Show logging status and enabled categories |
| `/log clear` | Clear the audit log channel |

## [Verification](verify.md)

| Command | Description |
|---|---|
| `/verify setup` | Setup the verification role and channel |
| `/verify send` | Send the verification panel |

## [Backups](bkp.md)

| Command | Description |
|---|---|
| `/bkp save` | Save current server configuration |
| `/bkp list` | List available backups |
| `/bkp load` | Load a server backup |
| `/bkp delete` | Delete backups in a category |

## [API tokens](api.md)

| Command | Description |
|---|---|
| `/api token create` | Create an API token (requires server owner or an active SUDO session) |
| `/api token list` | List this server's active API tokens |
| `/api token revoke` | Revoke an API token immediately |
| `/api docs` | How to configure Drew through the API |

## [Giveaways](giveaway.md)

| Command | Description |
|---|---|
| `/giveaway start` | Launch a new giveaway |
| `/giveaway end` | Force-end an active giveaway |
| `/giveaway reroll` | Reroll a winner for an ended giveaway |
| `/giveaway list` | List all active giveaways in this server |
| `/giveaway pause` | Pause an active giveaway (timer stops) |
| `/giveaway resume` | Resume a paused giveaway |
| `/giveaway delete` | Delete a giveaway permanently |

## [Antivirus](av.md)

| Command | Description |
|---|---|
| `/av scanfile` | Submit a file to VirusTotal for scanning |
| `/av scanweb` | Submit a URL to VirusTotal for scanning |
| `/av lookup` | Lookup a hash, URL, domain, or IP on VirusTotal |
| `/av history` | Show recent VirusTotal scans |
| `/av rescan` | Request a file rescan |
| `/av flags` | Show analysis flags for a VirusTotal analysis ID |

## [General](gen.md)

| Command | Description |
|---|---|
| `/gen help` | Show help menu |
| `/gen about` | Show bot info |
| `/gen ping` | Show latency |
| `/gen dashboard` | Manage everything |
| `/gen invite` | Invite link |
| `/gen infouser` | Show user info |
| `/gen infoserver` | Show server info |
| `/gen feedback` | Send feedback |
| `/gen report` | Report a user |
| `/gen snipe` | Snipe latest deleted message |
| `/gen editsnipe` | Snipe latest edited message |
| `/gen reactionsnipe` | Snipe latest removed reaction |
| `/gen clearsnipe` | Clear all snipes (Manage Messages req) |
| `/gen reactionhistory` | View reaction history for message |

## [Music](music.md)

| Command | Description |
|---|---|
| `/music play` | Play high-fidelity music from Spotify/Apple/Deezer |
| `/music skip` | Skip the current track |
| `/music stop` | Stop playback and clear queue |
| `/music queue` | Show current queue |
| `/music shuffle` | Shuffle the queue |
| `/music autoplay` | Toggle AutoPlay mode |
| `/music stay` | Toggle 24/7 mode |

## [VoiceMaster](voicemaster.md)

| Command | Description |
|---|---|
| `/setup default` | Create default Join to Create channel |
| `/setup predefined` | Channels with variable names |
| `/set channel` | Set Join to Create channel |
| `/set role` | Set moderator role |
| `/set bitrate` | Set default bitrate |
| `/toggle list` | Show all toggles |
| `/toggle set` | Set a toggle |
| `/voice lock` | Lock room |
| `/voice unlock` | Unlock room |
| `/voice ghost` | Hide room |
| `/voice unghost` | Unhide room |
| `/voice claim` | Claim room |
| `/voice limit` | Set limit |
| `/voice name` | Rename room |
| `/voice game` | Rename to activity |
| `/voice bitrate` | Set bitrate |
| `/voice permit` | Permit user |
| `/voice reject` | Reject user |
| `/voice status` | Set room status |
| `/voice region` | Set voice region |
| `/voice transfer` | Transfer ownership |
| `/voice text` | Toggle private text channel |
| `/interface` | Control panel |

## [Last.fm](lastfm.md)

| Command | Description |
|---|---|
| `/lastfm set` | Set your Last.fm username |
| `/lastfm np` | Show what you are currently playing |
| `/lastfm stats` | Show your Last.fm stats |
| `/lastfm milestone` | How many scrobbles until a milestone |
| `/lastfm playsalbum` | Check how many plays you have for an album |

## [Crypto](crypto.md)

| Command | Description |
|---|---|
| `/crypto` | Check cryptocurrency price |
| `/gas` | View current gas prices |
| `/transaction` | Get transaction info (BTC, LTC, ETH) |
| `/subscribe` | Subscribe to a BTC transaction for one confirmation |
