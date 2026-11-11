---
label: Antivirus
icon: bug
order: 910
---

# Antivirus

Check files, links, domains and IPs with VirusTotal.

## /av scanfile

Submit a file to VirusTotal for scanning.

| Option | Type | Required | Description |
|---|---|---|---|
| `file` | File | Yes | The file to scan (max 32MB) |

## /av scanweb

Submit a URL to VirusTotal for scanning.

| Option | Type | Required | Description |
|---|---|---|---|
| `url` | Text | Yes | URL to scan |

## /av lookup

Lookup a hash, URL, domain, or IP on VirusTotal.

| Option | Type | Required | Description |
|---|---|---|---|
| `query` | Text | Yes | Hash, URL, domain, or IP |
| `type` | Text | Yes | Lookup type (file, url, domain, ip) |

## /av history

Show recent VirusTotal scans.

## /av rescan

Request a file rescan.

| Option | Type | Required | Description |
|---|---|---|---|
| `hash` | Text | Yes | File hash (MD5/SHA1/SHA256) |

## /av flags

Show analysis flags for a VirusTotal analysis ID.

| Option | Type | Required | Description |
|---|---|---|---|
| `id` | Text | Yes | VirusTotal analysis ID |
