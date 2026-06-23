# Inventory And Sleep

Inventory death rules can change what happens to items after safe, frontier, and frontier PvP deaths. Sleep fast-forward is part of server controls and is enabled by default.

## Death Rules

When the inventory module is enabled, safe deaths can keep equipment and apply durability damage. If kept armor was equipped in an armor slot, it stays equipped after death.

Non-PvP deaths outside a managed worldborder can delete non-kept drops so items do not land on the ground.

PvP deaths outside the same managed frontier preserve normal loot drops so the killer and other players can loot as usual.

## Sleep Fast-Forward

When at least one eligible player sleeps, night advances faster. More sleeping players increase the speed, up to the configured cap.

The system ignores:

- AFK players.
- Players with `havennecessities.sleep.bypass`.
- Players in different worlds.

## Permission

- `havennecessities.inventory.bypass.death-rules` is a staff bypass and is not granted to operators unless staff explicitly grant it.

