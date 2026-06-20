# Admin Commands

HavenNecessities admin commands are available through `/havenadmin` and `/admin`.

## Economy Corrections

| Command | Description |
| --- | --- |
| `/havenadmin balance set <player> <amount>` | Set wallet balance. |
| `/havenadmin balance add <player> <amount>` | Add wallet balance. |
| `/havenadmin balance remove <player> <amount>` | Remove wallet balance. |
| `/havenadmin bank set <player> <amount>` | Set personal bank balance. |
| `/havenadmin bank add <player> <amount>` | Add personal bank balance. |
| `/havenadmin bank remove <player> <amount>` | Remove personal bank balance. |
| `/havenadmin serverbank set <amount>` | Set shared server bank balance. |
| `/havenadmin serverbank add <amount>` | Add to shared server bank. |
| `/havenadmin serverbank remove <amount>` | Remove from shared server bank. |

Wallet edits enforce wallet maximums. Personal bank edits enforce the player's current bank capacity. Remove actions cannot make balances negative.

## Professions

| Command | Description |
| --- | --- |
| `/havenadmin profession status <player>` | View profession state. |
| `/havenadmin profession addxp <player> <profession> <xp>` | Add profession XP. |
| `/havenadmin profession setxp <player> <profession> <xp>` | Set profession XP. |
| `/havenadmin profession removexp <player> <profession> <xp>` | Remove profession XP. |
| `/havenadmin profession setmain <player> <profession>` | Set main profession. |
| `/havenadmin profession sethobby <player> <profession>` | Set hobby profession. |
| `/havenadmin profession cooldown clear <player> <main|hobby|both>` | Clear role cooldowns. |
| `/havenadmin profession storage set <player> <slots|stack-size> <category> <amount>` | Set earned storage bonus. |
| `/havenadmin profession storage add <player> <slots|stack-size> <category> <amount>` | Add earned storage bonus. |

## Storage

| Command | Description |
| --- | --- |
| `/havenadmin storage view <player>` | View all stored items. |
| `/havenadmin storage view <player> <category>` | View one category. |
| `/havenadmin storage set <player> <category> <material> <amount>` | Set stored amount. |
| `/havenadmin storage add <player> <category> <material> <amount>` | Add stored items. |
| `/havenadmin storage remove <player> <category> <material> <amount>` | Remove stored items. |
| `/havenadmin storage clear <player> <category|all> confirm` | Clear stored items. |

## Worldborder

| Command | Description |
| --- | --- |
| `/havenadmin border status` | Show border status. |
| `/havenadmin border apply` | Apply configured border state. |
| `/havenadmin border set <world> <size>` | Set worldborder size. |
| `/havenadmin border expand <world> <blocks>` | Expand a worldborder. |
| `/havenadmin border reset <world>` | Reset a managed worldborder. |

## Server Controls

Server controls include `/admin time`, `/admin weather`, `/admin broadcast`, `/admin gamemode`, `/admin heal`, `/admin feed`, `/admin fly`, `/admin speed`, `/clearchat`, `/lockchat`, and moderation shortcuts.

OP and deop controls require separate permissions, `confirm`, and `op-controls.enabled: true`.
