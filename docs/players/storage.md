# Storage

The storage module gives players categorized item storage. It is disabled by default until the server enables it.

## Opening Storage

`/storage` opens the category menu. Each category button shows how many category slots are used, how many are unlocked, how many items are stored, and the current max stack per material slot.

`/storage <category>` opens that category's chest UI. The category screen opens even when the category has no stored items.

## Category Screens

Category screens can show:

- Stored material slots.
- Open unlocked slots.
- Locked slots.
- A back button to return to the category menu.

Locked slots show where future capacity can open up. Open slots are available for new stored material types.

## Depositing Items

Players can deposit in several ways:

- Run `/storage deposit <category>` to scan matching items from inventory.
- Shift-click a category button to quick-deposit matching inventory items.
- Click a category while holding a matching item to quick-deposit that held item.

Overflow stays in the player's inventory if the category is full or a stored material reaches its per-slot cap.

## Withdrawing Items

Players can run:

```text
/storage withdraw <category> <material> <amount>
```

In the category UI, clicking a stored item withdraws a stack, and shift-clicking withdraws as much as fits in the player's inventory.

## Slots And Stack Capacity

Storage is based on category slots. One unlocked category slot stores one material type. For example, if the Ores category has 3 unlocked slots, it can hold 3 distinct configured ore materials.

Each material slot also has a max stack capacity. This can be higher than a vanilla stack size and controls how many of that material can be stored in that slot.

## Item Safety

Items with different metadata stay separate. Durability, enchantments, custom names, lore, custom model data, and other item details are preserved so custom items do not collapse into unsafe shared stacks.

## Profession Growth

Professions can increase storage. Main profession level-ups can permanently add category slots and increase max stack size for related categories. Hobby profession level-ups do not grant storage growth by default.

If a profession death penalty lowers a player's level, storage bonuses above the new level become locked until the level is regained. The original rolls are reused when regained, so players cannot reroll storage bonuses by losing and regaining levels.

## Permissions

- `havennecessities.storage.use`
- `havennecessities.admin.storage`
