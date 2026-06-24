# Modules

HavenNecessities is organized into modules. Enable only the systems your server wants to use.

Use [Config Examples](config-examples.md) for copyable snippets and explanations of common customization keys.

| Module File | Feature |
| --- | --- |
| `modules/teleport.yml` | Spawn, homes, warps, player warps, teleport requests, RTP, warmups, cooldowns, and optional costs. |
| `modules/balance.yml` | Wallets, currency formatting, payment bounds, and balance placeholders. |
| `modules/bank.yml` | Personal banks, deposits, withdrawals, capacity tiers, and displayed interest. |
| `modules/serverbank.yml` | Shared server bank, contribution bounds, broadcasts, and milestones. |
| `modules/events.yml` | Vote-driven, scheduled, and random events. |
| `modules/servercontrols.yml` | Admin time, weather, broadcasts, gamemode, heal, feed, flight, speed, chat controls, moderation, OP/deop controls. |
| `modules/flight.yml` | Charged flight, recharge, sleep bonus, upgrades, meter display, soft landing, and world access. |
| `modules/inventory.yml` | Death inventory rules and frontier-aware loot handling. |
| `modules/worldborder.yml` | Soft frontier, warnings, damage, teleport blocking, placement blocking, PvP, scaling rewards. |
| `modules/claimsbridge.yml` | GriefPrevention integration, frontier claim blocking, claim storage, spawner trust checks, and RTP safety. |
| `modules/afk.yml` | Manual and automatic AFK status. |
| `modules/chat.yml` | Chat formatting, channels, item links, mentions, Discord bridge settings, tab header/footer, tab player names, and PvP marker. |
| `modules/cosmetics.yml` | Cosmetics hub, prefixes, join/leave messages, username/chat colors, particles, purchases, and custom text. |
| `modules/combat.yml` | Combat tags, anti-teleport, flight blocking, logout penalties, acknowledgement flow, PacketEvents health visuals. |
| `modules/professions.yml` | Main/hobby professions, XP, income, storage growth, stat perks, payouts, integrity rules. |
| `modules/storage.yml` | Categorized item storage, claim storage access, category UIs, capacity, aliases, and material lists. |
| `modules/toolbelt.yml` | Multi-Tool item, inventory-carried activation, legacy leggings attachment, slot storage, mending, and profession unlocks. |
| `modules/spawners.yml` | Haven spawner items, fragments, cores, essences, attunement, upgrades, placement limits, and claims checks. |
| `modules/profile.yml` | Player profile summaries across HavenNecessities systems. |
| `modules/rewards.yml` | Reusable reward packs for events and future systems. |

Shared source category definitions live in `sources.yml`.
