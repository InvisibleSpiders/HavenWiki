# Spawners

The spawners module adds Haven-managed spawner items, drops, attunement, upgrades, and claim-aware placement. It is disabled by default until staff enable it.

## Obtaining Items

Breaking spawners can drop Spawner Fragments, Spawner Cores, rare bound mob cores, and mob essences. Frontier spawners have higher default drop rates and are the default source for mob essences.

## Crafting

Default recipes include:

- Spawner Core from Spawner Fragments and an Echo Shard.
- Empty Spawner from Spawner Fragments, Iron Bars, and a Spawner Core.
- Spawner Altar from Spawner Fragments, Amethyst Shards, and a Lodestone.

Recipes can require Haven item IDs, so a vanilla item with the same material does not automatically count as the custom Haven item.

## Altar Attunement

The altar opens an anvil-style `1 + 2 = 3` UI. With the default `vanilla-material` mode, any lodestone can work as the altar. In `haven-item` mode, only the configured Haven altar item creates an altar.

Attuning an Empty Spawner consumes the matching mob essence each time. Cleansing an existing bound core removes its mob and can return some essence based on config.

## Placement And Upgrades

Placed Haven spawners track owner, mob, tier, and active state.

Players can right-click a placed Haven spawner with configured upgrade items to improve tier behavior such as spawn delays, spawn count, required player range, or spawn range.

Placement limits can cap spawners per chunk and per player. Certain mobs such as Wither, Ender Dragon, Warden, and Giant are blacklisted by default.

## Claims Rules

When ClaimsBridge is enabled, Haven spawners can require claimed land and GriefPrevention build trust. The same trust checks can apply to upgrades and altar use.

If a claim is unclaimed or resized away from a Haven spawner, the default orphan behavior leaves the block placed but marks it inactive.

