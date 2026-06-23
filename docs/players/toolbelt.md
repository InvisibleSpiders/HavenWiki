# Multi-Tool

The Multi-Tool stores one tool per slot type. It can be used as an inventory-carried item and still supports the legacy leggings attachment flow. The module is enabled by default.

## Getting Started

1. Craft the Multi-Tool item.
2. Carry it in your inventory, or combine it with leggings if your server uses the legacy attachment flow.
3. Run `/toolbelt` to add tools to your unlocked slots.

Your stored tools are saved to your player account, not to the item, so replacement tools open your own storage.

## Player Commands

| Command | Description |
| --- | --- |
| `/toolbelt` | Open your Multi-Tool storage. |
| `/toolbelt open` | Open your Multi-Tool storage. |
| `/toolbelt recipe` | Show the configured recipe in a read-only 3x3 preview. |
| `/toolbelt help` | Show command help. |

## Using Stored Tools

When the Multi-Tool is available and your main hand is empty, it can temporarily equip the matching stored tool for a block or entity interaction, then return the updated tool to storage.

Default slot types include pickaxe, axe, shovel, hoe, sword, shears, and brush.

## Paths And Farmland

Stored shovels and hoes can transform blocks:

- Normal right-click uses the configured normal action.
- Sneak-right-click uses the configured sneaking action.
- Shift-right-clicking air still opens the Multi-Tool UI.

By default, normal right-click prefers path creation and sneaking prefers tilling.

## Durability And Mending

Stored tools keep durability, enchantments, names, lore, custom model data, and other item data. If a stored tool is used, durability changes are saved back into the belt.

Mending can repair stored belt tools when you gain XP while wearing attached leggings, based on the configured XP-to-durability ratio.

## Unlocks

New players start with the configured base slot count. Additional slots unlock from overall profession level milestones.

## Examples

```text
/toolbelt recipe
/toolbelt
```

Player flow:

1. Craft a Multi-Tool.
2. Carry it or attach it to leggings if your server still uses attachment.
3. Store a pickaxe in an unlocked slot.
4. Empty your main hand and mine a matching block.

## Permissions

- `havennecessities.toolbelt.use`
- `havennecessities.toolbelt.craft`
