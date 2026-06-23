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

Personal bank capacity can use explicit configured levels or a formula-generated progression. Daily interest is paid on the player's first login of the day using the configured timezone.

## Interest Streaks

Daily login streaks can increase the personal bank interest rate. Missing days can decay the streak by a configured number of days before today's login is counted.

Players receive a login message when interest is paid.

## Server Bank

The server bank is a shared pool.

| Command | Description |
| --- | --- |
| `/serverbank` | View the shared balance and active milestone bonus. |
| `/serverbank deposit <amount>` | Contribute wallet money to the shared bank. |

Large contributions may broadcast depending on server configuration. Milestones can increase personal bank interest bonuses.

Events can also spend from the server bank when an event uses server-bank funding.
