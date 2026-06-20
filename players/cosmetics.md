# Cosmetics

The custom message module lets players manage cosmetic prefixes, join messages, and leave messages.

## Commands

| Command | Description |
| --- | --- |
| `/custommessage` or `/cosmetics` | Open the cosmetics menu. |
| `/custommessage prefix` | Manage prefixes. |
| `/custommessage join` | Manage join messages. |
| `/custommessage leave` | Manage leave messages. |
| `/custommessage select <prefix|join|leave> <id>` | Select an unlocked option. |
| `/custommessage buy <prefix|join|leave> <id>` | Buy a purchasable option. |
| `/custommessage custom <prefix|join|leave> <text...>` | Save custom text if permitted. |
| `/custommessage clear <prefix|join|leave>` | Clear a selected cosmetic. |

## Access Types

Cosmetics can be public, permission-gated, purchasable once with wallet money, or both permission-gated and purchasable.

Custom text allows only configured formatting tags. Unsafe tags are rejected.
