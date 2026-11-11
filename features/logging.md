---
label: Logging
icon: log
order: 70
---

# Logging

Drew posts server events to a log channel you choose.

## Categories

`message`, `member`, `moderation`, `channel`, `role`, `voice`, `invite` and `guild`. All are on by default. Turn any of them off with `/log toggle`.

## Set it up

1. `/log set channel:#logs`
2. Optional: `debounce` suppresses identical entries for a number of seconds.
3. Check the result with `/log status`.

Every configuration change made through commands, the dashboard or the API is also announced in the log channel, with who made it.
