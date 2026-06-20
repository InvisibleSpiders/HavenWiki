# Flight

The flight module provides charged flight. It is not always enabled.

## Commands

| Command | Description |
| --- | --- |
| `/fly` | Toggle charged flight. |
| `/flycharge` | View your current charge. |
| `/flyupgrade` | Buy the next efficiency tier. |

## How Charge Works

- Charge drains only while you are actively flying.
- Grounded, non-flying players recharge over time.
- Sleeping can grant an instant charge bonus.
- Efficiency upgrades increase how long each charge point lasts.
- If charge reaches zero midair, powered flight is disabled and soft landing protects you until ground contact.

Flight may be blocked during combat tags or outside a managed frontier.
