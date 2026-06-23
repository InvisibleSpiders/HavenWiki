# Cosmetics

The cosmetics module gives players one hub for visual and style options when it is enabled.

## Commands

| Command | Description |
| --- | --- |
| `/cosmetics` | Open the cosmetics hub. |
| `/cosmetics messages` | Open message and prefix cosmetics. |
| `/cosmetics username-color` | Open username color cosmetics. |
| `/cosmetics chat-color` | Open chat message color cosmetics. |
| `/cosmetics select <category> <id>` | Select an unlocked message cosmetic. |
| `/cosmetics buy <category> <id>` | Buy a purchasable message cosmetic. |
| `/cosmetics custom <category> <text...>` | Save custom text when permitted. |
| `/cosmetics clear <category>` | Clear the selected message cosmetic. |
| `/cosmetics particles` | Open particle effect slots. |
| `/cosmetics particles <slot>` | Open options for one particle slot. |

## Message Cosmetics

Players can select cosmetic prefixes, join messages, leave messages, username colors, and chat message colors from the cosmetics hub.

Premade cosmetics can be public for all players, permission gated, or purchasable once with wallet balance. Custom text can be limited by category, cooldown, maximum length, and allowed MiniMessage tags. Custom color categories accept a named color, hex color, or a permitted gradient such as `gradient:#ff66aa:#55ffff`.

## Particle Slots

Particles can be configured for:

- Walking trails.
- Flight trails.
- Swimming trails.
- Frontier trails while outside a managed worldborder frontier.
- Teleport departure effects.
- Teleport arrival effects.

Staff can make particle effects free, permission-only, or purchasable with in-game money.

## Examples

```text
/cosmetics
/cosmetics username-color
/cosmetics custom username-color #ff66aa
/cosmetics custom chat-color gradient:#ff66aa:#55ffff
/cosmetics particles flight
```

## Permissions

- `havennecessities.cosmetics.use`
- `havennecessities.cosmetics.custom`
- `havennecessities.cosmetics.custom.prefix`
- `havennecessities.cosmetics.custom.join`
- `havennecessities.cosmetics.custom.leave`
- `havennecessities.cosmetics.custom.username-color`
- `havennecessities.cosmetics.custom.chat-color`
- `havennecessities.cosmetics.custom.gradient`
- `havennecessities.cosmetics.custom.gradient.username-color`
- `havennecessities.cosmetics.custom.gradient.chat-color`
- `havennecessities.cosmetics.particles.flight.witch`
