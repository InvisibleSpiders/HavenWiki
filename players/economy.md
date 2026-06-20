# Economy

The balance module provides player wallets. Wallet money is used by `/pay`, personal banks, server bank contributions, flight upgrades, custom message purchases, and optional teleport costs.

## Wallet Balance

| Command | Description |
| --- | --- |
| `/balance` or `/bal` | View your wallet balance. |
| `/pay <player> <amount>` | Pay another online player. |

`/pay` targets online players and rejects self-payments.

## Optional Costs

Servers can configure wallet costs for teleport actions. Cost bypasses are controlled by staff permissions.

## Placeholders

When PlaceholderAPI is installed and the balance module is enabled, HavenNecessities can provide:

- `%havennecessities_balance%`
- `%havennecessities_balance_raw%`
- `%havennecessities_currency_name%`
