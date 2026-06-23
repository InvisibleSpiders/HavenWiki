# Teleportation

The teleport module covers spawn, homes, server warps, player warps, TPA, and RTP. Staff setup and coordinate teleport commands are documented in [Admin Commands](../admins/admin-commands.md).

## Player Teleports

| Command | Purpose |
| --- | --- |
| `/spawn` | Teleport to the server spawn. |
| `/home [name]` | Teleport to one of your homes. |
| `/sethome [name]` | Save a home at your current location. |
| `/delhome <name>` | Delete a saved home. |
| `/homes` | List saved homes. |
| `/warp <name>` | Teleport to a server warp. |
| `/warps` | List server warps. |
| `/pwarp <player|warp> [warp]` | Teleport to a player warp. |
| `/pwarps [player]` | List player warps. |
| `/tpa <player>` | Request to teleport to another player. |
| `/tpahere <player>` | Request that another player teleports to you. |
| `/tpaccept` | Accept a pending teleport request. |
| `/tpdeny` | Deny a pending teleport request. |
| `/rtp` | Randomly teleport in the configured world range. |

## Warmups And Cooldowns

Teleport warmups can be cancelled by movement, damage, or logout depending on config. Cooldowns are configured per teleport type.

## Costs

Teleport costs are disabled by default. When the balance module is enabled and teleport cost charging is enabled, costs are checked before warmup and charged only after a successful teleport.

## Frontier Safety

When the worldborder module is enabled, teleport commands can be blocked from leaving or entering the frontier depending on worldborder settings. The bypass permission is intentionally separate so moderation staff can be granted it explicitly.

## Claim Safety

When ClaimsBridge is enabled, teleport features can avoid protected land. Random teleport can be configured to avoid sending players into claimed land.

## Permissions

- `havennecessities.teleport.spawn`
- `havennecessities.teleport.home`
- `havennecessities.teleport.sethome`
- `havennecessities.teleport.delhome`
- `havennecessities.teleport.homes`
- `havennecessities.teleport.warp`
- `havennecessities.teleport.warps`
- `havennecessities.teleport.playerwarp`
- `havennecessities.teleport.setplayerwarp`
- `havennecessities.teleport.delplayerwarp`
- `havennecessities.teleport.pwarps`
- `havennecessities.teleport.tpa`
- `havennecessities.teleport.tpahere`
- `havennecessities.teleport.tpaccept`
- `havennecessities.teleport.tpdeny`
- `havennecessities.teleport.rtp`
