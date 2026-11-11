---
label: Backups
icon: database
order: 940
---

# Backups

Save your server configuration and restore it later.

!!!info Who can use it
By default, members with **Administrator**. Server admins can change this in Server Settings, Integrations.
!!!

## /bkp save

Save current server configuration.

| Option | Type | Required | Description |
|---|---|---|---|
| `category` | Text | Yes | Backup category (full, security, limits, punishments, channels) |
| `label` | Text | No | Optional label for this backup |

## /bkp list

List available backups.

## /bkp load

Load a server backup.

| Option | Type | Required | Description |
|---|---|---|---|
| `category` | Text | Yes | Backup category to load. Values: `full`, `security`, `limits`, `punishments`, `channels`. |

## /bkp delete

Delete backups in a category.

| Option | Type | Required | Description |
|---|---|---|---|
| `category` | Text | Yes | Category to clear. Values: `full`, `security`, `limits`, `punishments`, `channels`. |
