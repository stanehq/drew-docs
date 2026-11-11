---
label: Crypto
icon: graph
order: 860
---

# Crypto

Prices, gas fees and transaction lookups.

## /crypto

Check cryptocurrency price.

| Option | Type | Required | Description |
|---|---|---|---|
| `crypto` | Text | Yes | The crypto (e.g. bitcoin, ethereum) |
| `currency` | Text | No | Currency (default: usd) |

## /gas

View current gas prices.

## /transaction

Get transaction info (BTC, LTC, ETH).

| Option | Type | Required | Description |
|---|---|---|---|
| `hash` | Text | Yes | Transaction hash |

## /subscribe

Subscribe to a BTC transaction for one confirmation.

| Option | Type | Required | Description |
|---|---|---|---|
| `hash` | Text | Yes | BTC Transaction hash |
