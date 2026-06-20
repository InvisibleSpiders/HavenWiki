# Teleportation

HavenNecessities supports spawn, homes, server warps, player warps, teleport requests, and random teleport.

## Homes

Use `/sethome [name]` to save a home and `/home [name]` to return to it. Use `/homes` to list homes and `/delhome <name>` to remove one.

Servers can configure home limits. Some servers may grant limit permissions such as `havennecessities.teleport.homes.<number>`.

## Warps

Server warps are public anchors created by staff. Use `/warps` to list them and `/warp <name>` to teleport.

Player warps are player-owned anchors. Use `/setpwarp <name>`, `/pwarps [player]`, `/pwarp <player|warp> [warp]`, and `/delpwarp <name>`.

## Teleport Requests

Use `/tpa <player>` to ask to teleport to someone, or `/tpahere <player>` to ask them to teleport to you. Requests can be accepted with `/tpaccept` or denied with `/tpdeny`.

## Random Teleport

`/rtp` searches for a safe random location using the server's configured radius and safety checks.

## Costs, Warmups, And Cooldowns

Servers can enable warmups, cooldowns, and wallet costs. If teleport costs are enabled, charges happen after a successful warmup, not when a cancelled warmup begins.

Worldborder and combat modules may block teleporting in dangerous situations.
