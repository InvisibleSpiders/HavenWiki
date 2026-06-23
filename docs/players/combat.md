# Combat

The combat module protects PvP from escape abuse. It is enabled by default.

## Combat Tags

Valid PvP damage can tag both players for a configured duration. While tagged:

- Teleport escapes can be blocked.
- Charged flight can be disabled.
- A boss bar may show the remaining tag time.

## Logging Out

If a tagged player logs out, the server can apply a combat-log penalty. The player may need to acknowledge the penalty after rejoining before they can continue normally.

If dialogs are unavailable, `/combatconfirm` is the fallback command.

## Health Visuals

PacketEvents health visuals can show temporary client-side health bars and damage indicators around damaged entities. If PacketEvents is unavailable, the feature is skipped instead of falling back to real entities.

## Frontier Flight

Charged flight can also be blocked in dangerous frontier areas beyond a managed worldborder.
