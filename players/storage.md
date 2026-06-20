# Storage

Storage lets players keep configured item categories in a server-managed storage system.

## Commands

| Command | Description |
| --- | --- |
| `/storage` | Open the category overview. |
| `/storage <category>` | View one category. |
| `/storage deposit <category>` | Deposit matching inventory items. |
| `/storage withdraw <category> <material> <amount>` | Withdraw items. |

## How It Works

- Each category has a number of unlocked material slots.
- One slot stores one material type.
- Each material slot has a max stack size.
- If a category is full, overflow stays in your inventory.
- Clicking a category while holding a matching item can quick-deposit it.
- Shift-clicking a category can deposit matching inventory items.

Profession level-ups can permanently increase category slots and stack sizes.
