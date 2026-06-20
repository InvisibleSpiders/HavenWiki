# Banks

HavenNecessities has two bank systems: personal banks for each player and a shared server bank.

## Personal Bank

Your personal bank stores money separately from your wallet.

| Command | Description |
| --- | --- |
| `/bank` | View your bank balance, capacity, level, and displayed interest bonus. |
| `/bank upgrade` | Buy the next configured capacity tier. |
| `/deposit <amount>` | Move wallet money into your bank. |
| `/withdraw <amount>` | Move bank money back to your wallet. |

Personal bank capacity can be upgraded when the server has configured capacity tiers.

## Server Bank

The server bank is a shared pool.

| Command | Description |
| --- | --- |
| `/serverbank` | View the shared balance and active milestone bonus. |
| `/serverbank deposit <amount>` | Contribute wallet money to the shared bank. |

Large contributions may broadcast depending on server configuration. Milestones can affect displayed bonuses.
