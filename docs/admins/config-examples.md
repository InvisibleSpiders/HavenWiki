# Config Examples

These examples show common HavenNecessities customization patterns. They are partial snippets: copy the keys into the matching file and keep any omitted keys from your existing config.

Every module has an `enabled` switch. Keep experimental or unsupported systems disabled until the server has the needed permissions, dependencies, and testing time.

## Core Setup

File: `config.yml`

```yaml
storage:
  type: sqlite
  sqlite:
    file: havennecessities.db
integrations:
  placeholderapi:
    enabled: true
  vaultunlocked:
    enabled: true
dialogs:
  enabled: true
  provider: auto
time:
  timezone: America/Edmonton
startup:
  module-failure-policy: isolate
diagnostics:
  log-module-startup: true
```

What each function does:

- `storage.type` selects the data backend. Keep it as `sqlite`; MySQL and MariaDB are reserved for future support.
- `storage.sqlite.file` names the database file in the plugin data folder.
- `integrations.placeholderapi.enabled` lets supported placeholders resolve when PlaceholderAPI is installed.
- `integrations.vaultunlocked.enabled` lets economy integrations use VaultUnlocked when available.
- `dialogs.enabled` allows Paper dialog UIs where modules support them.
- `dialogs.provider: auto` lets the plugin choose the best available dialog provider.
- `time.timezone` controls calendar systems such as event schedules and daily bank interest. Use `server` to inherit the JVM timezone.
- `startup.module-failure-policy: isolate` keeps the plugin online if an optional module fails during startup.
- `diagnostics.log-module-startup` writes module startup details to console for easier troubleshooting.

## Teleport

File: `modules/teleport.yml`

```yaml
enabled: true
costs:
  charging-enabled: true
  spawn: 0.0
  home: 25.0
  warp: 50.0
  player-warp: 50.0
  rtp: 250.0
warmups:
  spawn: 3
  home: 3
  rtp: 5
cooldowns:
  spawn: 30
  home: 30
  rtp: 300
homes:
  default-limit: 3
player-warps:
  default-limit: 1
claims:
  destinations:
    enabled: true
    allow-owner: true
    allow-trusted: true
  placements:
    enabled: true
    allow-owner: true
    allow-trusted: true
  rtp:
    avoid-claimed-land: true
rtp:
  worlds:
    world:
      enabled: true
      center: spawn
      min-radius: 250
      max-radius: 5000
      max-attempts: 32
```

What each function does:

- `costs.charging-enabled` turns wallet costs on for teleport actions.
- Each value under `costs` is the wallet amount charged for that teleport type.
- `warmups` delays the teleport so players cannot instantly escape danger.
- `cooldowns` throttles repeated use after a successful teleport.
- `homes.default-limit` controls how many homes a normal player can set.
- `player-warps.default-limit` controls how many public player warps a player can create.
- `claims.destinations` blocks teleport destinations inside protected claims unless the player is owner, trusted, or bypassed.
- `claims.placements` blocks saving homes and warps inside protected claims.
- `claims.rtp.avoid-claimed-land` prevents random teleport from dropping players into private builds.
- `rtp.worlds.<world>` controls where random teleport searches and how far from the center it can place players.

## Economy And Banks

Files: `modules/balance.yml`, `modules/bank.yml`, `modules/serverbank.yml`

```yaml
# modules/balance.yml
enabled: true
currency:
  singular: coin
  plural: coins
  symbol: "$"
  decimal-places: 2
wallets:
  starting-balance: "100.00"
  maximum-balance: "1000000000.00"
payments:
  minimum: "0.01"
  maximum: "1000000.00"
  allow-offline-targets: false
```

```yaml
# modules/bank.yml
enabled: true
capacity:
  mode: levels
  default: "10000.00"
  levels:
    0:
      capacity: "10000.00"
      cost: "0.00"
    1:
      capacity: "25000.00"
      cost: "5000.00"
interest:
  enabled: true
  timezone: server
  base-rate-percent: "1.00"
  streak:
    enabled: true
    increment-percent: "0.10"
    max-bonus-percent: "1.00"
```

```yaml
# modules/serverbank.yml
enabled: true
deposits:
  minimum: "0.01"
  maximum: "1000000.00"
  broadcast-threshold: "1000.00"
milestones:
  - balance: "100000.00"
    interest-bonus-percent: "0.25"
```

What each function does:

- `currency` controls how balances display in chat, menus, and placeholders.
- `wallets.starting-balance` gives new players their first wallet balance.
- `wallets.maximum-balance` caps wallet storage.
- `payments.minimum` and `payments.maximum` protect against tiny spam payments and huge accidental transfers.
- `payments.allow-offline-targets` decides whether `/pay` can target offline players.
- `capacity.mode: levels` uses explicit bank tiers. Use `formula` when you want generated tiers.
- `capacity.levels` defines bank capacity and upgrade cost per level.
- `interest.enabled` pays bank interest on a player's first login of the day.
- `interest.streak` adds a daily-login bonus and caps that bonus.
- `serverbank.deposits.broadcast-threshold` announces large community contributions.
- `serverbank.milestones` adds server-wide interest bonuses as the shared bank grows.

## Events And Rewards

Files: `modules/events.yml`, `modules/rewards.yml`

```yaml
# modules/events.yml
enabled: true
votes:
  duration-seconds: 120
  pass-ratio: 0.60
  minimum-votes: 3
  reroll:
    enabled: true
    minimum-votes: 3
    pass-ratio: 0.60
scheduler:
  enabled: true
  interval-minutes: 180
  cooldown-minutes: 60
  minimum-online-players: 3
  random:
    enabled: true
    interval-seconds: 600
events:
  frontier-surge:
    enabled: true
    type: frontier-surge
    display-name: "Frontier Surge"
    vote-required: true
    funding:
      mode: none
    world: world
    surge-profile: "ominous_frontier"
    launches:
      admin:
        enabled: true
      random:
        enabled: true
        weight: 8
        cooldown-minutes: 360
```

```yaml
# modules/rewards.yml
enabled: true
packs:
  frontier_vote_bonus:
    enabled: true
    grant-mode: yes-voters-online
    commands:
      - "say <player> helped fund <event>."
    economy:
      amount: "250.00"
    loot-pools:
      frontier_supplies:
        rolls: 2
        entries:
          diamonds:
            material: DIAMOND
            chance: 0.25
            min-amount: 1
            max-amount: 3
            weight: 3
```

What each function does:

- `votes.duration-seconds` controls how long players have to vote.
- `votes.pass-ratio` is the fraction of yes votes required to pass.
- `votes.minimum-votes` prevents one or two players from passing server-wide events.
- `votes.reroll` lets players reject a random event and roll another eligible event.
- `scheduler.interval-minutes` controls fixed scheduling cadence.
- `scheduler.random.interval-seconds` controls how often the random scheduler checks for eligible events.
- `events.<id>.type` chooses the event executor, such as `frontier-surge`, `worldborder-expand`, or `command-reward`.
- `funding.mode: none` runs a world event without server-bank cost. Use `server-bank` for funded events.
- `launches.admin`, `launches.random`, and `launches.fixed` decide how an event can start.
- `rewards.packs` define reusable reward bundles for events and future systems.
- `grant-mode: yes-voters-online` rewards online players who voted yes.
- `commands`, `economy`, and `loot-pools` let one pack combine console commands, wallet payouts, and item drops.

## Worldborder And Frontier

File: `modules/worldborder.yml`

```yaml
enabled: true
managed-worlds:
  world:
    center: spawn
    initial-size: 5000
    maximum-size: 25000
    frontier:
      minimum-distance: 500
    warning-distance: 50
    scaling:
      distance-step: 250.0
      max-scaling-steps: 40
      damage:
        base: 1.0
        per-step: 0.35
        max: 20.0
      hazard-mobs:
        enabled: true
        per-player-cap: 4
        allowed-types:
          - ZOMBIE
          - SKELETON
          - SPIDER
    surges:
      ominous_frontier:
        enabled: true
        duration-seconds: 900
        wave-interval-seconds: 90
        wave-count: 8
    teleport-block:
      enabled: true
    placement-block:
      enabled: true
```

What each function does:

- `managed-worlds.<world>` defines each world with a soft frontier.
- `initial-size` is the starting safe border size.
- `maximum-size` caps permanent expansion.
- `frontier.minimum-distance` separates the safe border from frontier systems.
- `warning-distance` controls when approach warnings begin.
- `scaling.distance-step` defines how many blocks outside the border count as one danger step.
- `scaling.damage` controls periodic frontier damage and how it grows with distance.
- `hazard-mobs` controls frontier mob pressure, caps, allowed mobs, equipment, and scaling.
- `surges` defines temporary frontier wave profiles that events can launch.
- `teleport-block` and `placement-block` prevent escaping or anchoring in unsafe areas.

## Storage And Claim Storage

File: `modules/storage.yml`

```yaml
enabled: true
fallback-category: general
claim-storage:
  enabled: true
  deleted-claim-grace-days: 14
  capacity:
    base-slots: 54
    size-blocks-per-slot: 500
    activity-points-per-slot: 25
    max-slots: 540
    max-stack-per-slot: 4096
  access:
    owner:
      view: true
      deposit: true
      withdraw: true
      manage: true
    trusted:
      view: true
      deposit: true
      withdraw: true
      manage: false
categories:
  ores:
    display-name: "Ores"
    base-slots: 3
    max-slots: 90
    base-stack-per-slot: 256
    max-stack-per-slot: 4096
    aliases: ["ore", "mining"]
    source-categories:
      - ORES
      - RAW_ORES
      - GEMS
```

What each function does:

- `fallback-category` is the catch-all category for workflows that need a default.
- `claim-storage.enabled` turns on shared claim-owned storage.
- `deleted-claim-grace-days` controls how long deleted-claim storage is retained before cleanup.
- `capacity.base-slots` gives every claim a starting capacity.
- `size-blocks-per-slot` and `activity-points-per-slot` let larger or more active claims earn more storage.
- `access` maps claim relationships to storage actions.
- `categories.<id>` defines one player storage category.
- `base-slots` and `max-slots` control how many distinct material stacks fit.
- `base-stack-per-slot` and `max-stack-per-slot` control how much of each material fits.
- `aliases` let players use alternate category names in commands.
- `source-categories` imports material groups from `sources.yml`.

## Multi-Tool

File: `modules/toolbelt.yml`

```yaml
enabled: true
item:
  material: LEATHER_HORSE_ARMOR
  name: "<gold>Multi-Tool</gold>"
  custom-model-data: 10001
recipe:
  enabled: true
  require-permission: false
activation:
  mode: both
  require-empty-main-hand: true
  reclaim-delay-ticks: 20
interactions:
  pathing:
    enabled: true
  tilling:
    enabled: true
mending:
  enabled: true
  durability-per-xp: 2
progression:
  base-slots: 3
  max-slots: 9
  source: OVERALL_PROFESSION_LEVEL
  unlocks:
    5: 4
    10: 5
```

What each function does:

- `item` customizes the physical Multi-Tool material, name, lore, model data, glow, and tooltip behavior.
- `recipe.enabled` registers or disables the crafting recipe.
- `recipe.require-permission` requires `havennecessities.toolbelt.craft` before crafting.
- `activation.mode` controls whether the tool works from inventory, legacy leggings, or both.
- `require-empty-main-hand` prevents the Multi-Tool from replacing an item the player is holding.
- `reclaim-delay-ticks` controls how quickly a temporary tool returns to storage.
- `interactions.pathing` and `interactions.tilling` control shovel and hoe right-click behavior.
- `mending` repairs stored tools from XP because they are not always in vanilla inventory.
- `progression.unlocks` maps overall profession level to unlocked slot count.

## Spawners And ClaimsBridge

Files: `modules/spawners.yml`, `modules/claimsbridge.yml`

```yaml
# modules/spawners.yml
enabled: true
altar:
  mode: vanilla-material
  material: LODESTONE
drops:
  normal:
    fragment-chance: 0.65
    core-chance: 0.04
    essence-chance: 0.0
  frontier:
    fragment-chance: 0.90
    core-chance: 0.08
    essence-chance: 0.10
placement:
  max-per-chunk: 8
  max-per-player: 24
upgrades:
  max-tier: 3
  tiers:
    1:
      required-item: spawner_core
      required-amount: 1
      min-delay-ticks: 180
```

```yaml
# modules/claimsbridge.yml
enabled: true
provider: griefprevention
frontier:
  prevent-claims: true
spawners:
  require-claimed-land: true
  require-build-trust: true
  require-upgrade-trust: true
  require-altar-trust: true
  orphan-mode: inactive
```

What each function does:

- `altar.mode: vanilla-material` lets normal lodestones act as attunement altars.
- `altar.mode: haven-item` requires the configured custom Haven altar item.
- `drops.normal` controls ordinary spawner break rewards.
- `drops.frontier` controls higher-risk frontier spawner rewards.
- `items` defines custom fragments, cores, essences, and altar items.
- `recipes` defines how custom spawner items are crafted.
- `mobs.<mob>` enables each mob and maps it to essence and bound-core items.
- `placement.max-per-chunk` and `max-per-player` control spawner density.
- `upgrades.tiers` defines upgrade costs and behavior changes per tier.
- `claimsbridge.provider` selects the claims plugin integration.
- `frontier.prevent-claims` blocks new claims in frontier areas.
- `spawners.require-claimed-land` requires protected land before placement.
- `require-build-trust`, `require-upgrade-trust`, and `require-altar-trust` protect player claims.
- `orphan-mode: inactive` disables Haven spawners that are no longer inside their required claim.

## Chat And Discord

File: `modules/chat.yml`

```yaml
enabled: true
chat:
  enabled: true
  format: "<gray><pvp_marker><prefix></gray> <white><player></white> <dark_gray>></dark_gray> <message>"
channels:
  market:
    enabled: true
    cooldown-seconds: 60
    shortcut-prefixes: ["#", "$"]
    format: "<gold>[Market]</gold> <player><gray>: </gray><message>"
discord:
  enabled: false
  require-linked-for-inbound-chat: true
rich-content:
  item-links:
    enabled: true
    tokens: ["[item]", "[i]"]
  mentions:
    enabled: true
    ignore-self: true
tab:
  enabled: true
  refresh-interval-ticks: 40
```

What each function does:

- `chat.format` controls the default in-game chat line.
- `channels.<id>` defines specialty channels such as global, market, or staff.
- `cooldown-seconds` throttles noisy channels.
- `shortcut-prefixes` lets players route messages by prefix.
- `discord.enabled` turns on the Discord bridge only after safe bot setup.
- `require-linked-for-inbound-chat` requires Discord users to link before speaking into Minecraft.
- `rich-content.item-links` lets players type `[item]` or `[i]`.
- `rich-content.mentions` highlights online players and sends notifications.
- `tab` controls tab header, footer, and player list name formatting.

## Combat And Inventory

Files: `modules/combat.yml`, `modules/inventory.yml`

```yaml
# modules/combat.yml
enabled: true
tag:
  duration-seconds: 15
  refresh-on-hit: true
teleport-block:
  enabled: true
flight-block:
  enabled: true
logout-penalty:
  enabled: true
  mode: death
acknowledgement:
  enabled: true
  prefer-dialogs: true
bossbar:
  enabled: true
health-visuals:
  enabled: true
  viewer-radius-blocks: 16.0
```

```yaml
# modules/inventory.yml
enabled: true
rules:
  safe:
    keep-equipment: true
    equipment-keep-chance: 100.0
    drop-behavior: VANILLA
  worldborder-outside:
    keep-equipment: true
    equipment-keep-chance: 30.0
    drop-behavior: DELETE
  worldborder-outside-pvp:
    keep-equipment: false
    drop-behavior: VANILLA
```

What each function does:

- `tag.duration-seconds` controls how long a PvP combat tag lasts.
- `refresh-on-hit` extends the tag when another valid hit lands.
- `teleport-block` and `flight-block` stop escape tools during combat.
- `logout-penalty.mode: death` punishes combat logging by applying death.
- `acknowledgement` shows a dialog or fallback command after combat logging.
- `bossbar` shows remaining combat-tag time.
- `health-visuals` enables PacketEvents client-side health bars and damage text.
- `inventory.rules.safe` controls ordinary death behavior.
- `worldborder-outside` controls non-PvP frontier death behavior.
- `worldborder-outside-pvp` controls PvP death behavior in the frontier.
- `drop-behavior: DELETE` removes non-kept drops instead of leaving them on the ground.

## UI And Message Customization

Many modules support MiniMessage text, menu item materials, chest slots, dialog bodies, and placeholders.

```yaml
ui:
  prefer-dialogs: true
  fallback: chest
  dialog:
    title: "<gold>Bank</gold>"
    body:
      - "<gray>Bank: <aqua><balance>/<capacity></aqua></gray>"
  chest:
    title: "<gold>Bank</gold>"
    rows: 3
messages:
  no-permission: "<red>You do not have permission.</red>"
```

What each function does:

- `prefer-dialogs` uses Paper dialogs when available.
- `fallback: chest` keeps a chest-style UI available when dialogs are unavailable.
- `dialog.title`, `dialog.body`, and button labels support MiniMessage formatting.
- `chest.rows` accepts 1-6 rows.
- Chest `slot` values are zero-based positions inside `rows * 9`.
- `material`, `name`, `lore`, `glow`, and `hide-tooltip` customize menu items.
- `messages` lets staff change player-facing text without code changes.

