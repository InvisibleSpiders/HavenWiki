# Tool Belt

The Tool Belt stores one tool per slot type and works while you are wearing leggings with a Tool Belt attached. The module is enabled by default.

## Getting Started

1. Craft the Tool Belt item.
2. Combine the Tool Belt with leggings in your 2x2 player crafting grid or a crafting table.
3. Equip the attached leggings.
4. Run `/toolbelt` to add tools to your unlocked slots.

The physical Tool Belt item is consumed when it is attached. Your stored tools are saved to your player account, not to the item, so replacement belts open your own storage.

## Player Commands

| Command | Description |
| --- | --- |
| `/toolbelt` | Open your Tool Belt storage. |
| `/toolbelt recipe` | Show the configured recipe in a read-only 3x3 preview. |
| `/toolbelt help` | Show command help. |

## Using Stored Tools

When attached leggings are equipped and your main hand is empty, the belt can temporarily equip the matching stored tool for a block or entity interaction, then return the updated tool to storage.

Default slot types include pickaxe, axe, shovel, hoe, sword, shears, and brush.

## Paths And Farmland

Stored shovels and hoes can transform blocks:

- Normal right-click uses the configured normal action.
- Sneak-right-click uses the configured sneaking action.
- Shift-right-clicking air still opens the Tool Belt UI.

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

1. Craft a Tool Belt.
2. Combine it with leggings.
3. Wear the leggings.
4. Store a pickaxe in an unlocked slot.
5. Empty your main hand and mine a matching block.

## Permissions

- `havennecessities.toolbelt.use`
- `havennecessities.toolbelt.craft`
