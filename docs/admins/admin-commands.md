# Admin Commands

HavenNecessities admin commands are available through `/havenadmin` and `/admin`.

## Staff Teleport

| Command | Description |
| --- | --- |
| `/setspawn` | Set the server spawn at your current location. |
| `/setwarp <name>` | Create or replace a server warp at your current location. |
| `/delwarp <name>` | Delete a server warp. |
| `/tppos <x> <y> <z> [player] [world]` | Teleport yourself or another player to coordinates. |

Examples:

```text
/setwarp mines
/delwarp oldmarket
/tppos 100 80 -250
/tppos 100 80 -250 Steve
/tppos ~1 ~ ~-2 Steve
```

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

## Claim Storage

| Command | Description |
| --- | --- |
| `/admin claimstorage inspect [claimId]` | Inspect claim storage state. |
| `/admin claimstorage setslots <claimId> <slots>` | Set claim storage capacity. |
| `/admin claimstorage lock <claimId> [reason]` | Lock claim storage. |
| `/admin claimstorage unlock <claimId>` | Unlock claim storage. |
| `/admin claimstorage purge <claimId> confirm` | Delete stored claim contents. |
| `/admin claimstorage transfer <fromClaimId> <toClaimId>` | Transfer claim storage contents. |

## Multi-Tool

| Command | Description |
| --- | --- |
| `/havenadmin toolbelt view <player>` | View or edit a player's Multi-Tool storage. |
| `/havenadmin toolbelt give <player>` | Give the physical Multi-Tool item to an online player. |
| `/havenadmin toolbelt clear <player> confirm` | Clear stored Multi-Tool tools. |

## Events

| Command | Description |
| --- | --- |
| `/havenadmin event start <event-id>` | Start a configured event. |
| `/havenadmin event cancel` | Cancel the active event. |
| `/havenadmin event status` | Inspect the active event. |

## Worldborder

| Command | Description |
| --- | --- |
| `/havenadmin border status` | Show border status. |
| `/havenadmin border apply` | Apply configured border state. |
| `/havenadmin border set <world> <size>` | Set worldborder size. |
| `/havenadmin border expand <world> <blocks>` | Expand a worldborder. |
| `/havenadmin border reset <world>` | Reset a managed worldborder. |

## Spawners And ClaimsBridge

| Command | Description |
| --- | --- |
| `/spawners give <player> <item-id> [amount]` | Give a configured Haven spawner item. |
| `/spawners inspect` | Inspect the placed Haven spawner you are looking at. |
| `/spawners setmob <mob>` | Change a Haven spawner mob. |
| `/spawners setlevel <level>` | Change a Haven spawner tier. |
| `/spawners activate` | Mark a Haven spawner active. |
| `/spawners deactivate` | Mark a Haven spawner inactive. |
| `/spawners transfer <player>` | Transfer spawner ownership. |
| `/spawners reload` | View spawner reload guidance. |
| `/admin claimsbridge status` | Show ClaimsBridge status. |
| `/admin claimsbridge inspect` | Inspect the current claim context. |
| `/admin claimsbridge scan` | Scan claim-linked Haven systems. |
| `/admin claimsbridge reactivate` | Reactivate eligible orphaned spawners. |

## Server Controls

Server controls include `/admin time`, `/admin weather`, `/admin broadcast`, `/admin gamemode`, `/admin heal`, `/admin feed`, `/admin fly`, `/admin speed`, `/clearchat`, `/lockchat`, and moderation shortcuts.

## Staff Chat

| Command | Description |
| --- | --- |
| `/staffchat <message>` | Send a staff-channel message. |
| `/chat staff <message>` | Send a message to the staff channel. |

Shortcut examples:

```text
! Need a second look at spawn
@ Player report in global
```

## Item Tools

| Command | Description |
| --- | --- |
| `/admin item rename <name...>` | Rename the held item with MiniMessage formatting. |
| `/admin item lore add <line...>` | Add held item lore. |
| `/admin item lore set <line-number> <line...>` | Replace a lore line. |
| `/admin item lore remove <line-number>` | Remove a lore line. |
| `/admin item lore clear` | Clear held item lore. |
| `/admin item enchant <enchantment> <level> [--unsafe|-u]` | Add an enchantment. |
| `/admin item enchant remove <enchantment>` | Remove an enchantment. |
| `/admin item enchant clear` | Clear enchantments. |
| `/admin item repair` | Repair the held item. |
| `/admin item repair all` | Repair repairable items in your inventory. |
| `/admin item repair toolbelt` | Repair stored tools in your own Multi-Tool. |
| `/admin item repair all-with-toolbelt` | Repair inventory and stored Multi-Tool tools. |

Unsafe enchantments require both `--unsafe` or `-u` and `havennecessities.admin.item.unsafe`.

OP and deop controls require separate permissions, `confirm`, and `op-controls.enabled: true`.
