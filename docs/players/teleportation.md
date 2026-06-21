# Teleportation

The teleport module covers spawn, homes, server warps, player warps, TPA, RTP, and coordinate teleports.

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

## Coordinate Teleport

`/tppos <x> <y> <z> [player] [world]` is an admin coordinate teleport command.

Examples:

```text
/tppos 100 80 -250
/tppos 100 80 -250 Steve
/tppos 100 80 -250 Steve world_nether
/tppos ~1 ~ ~-2 Steve
```

Behavior:

- With no player argument, `/tppos` teleports the command sender.
- With a player but no world, it teleports that player in the target player's current world.
- With a player and world, it teleports that player in the provided world.
- Console must provide a player name.
- `~`, `~1`, and `~-2` relative coordinates are supported relative to the target player's current location.

## Warmups And Cooldowns

Teleport warmups can be cancelled by movement, damage, or logout depending on config. Cooldowns are configured per teleport type.

## Costs

Teleport costs are disabled by default. When the balance module is enabled and teleport cost charging is enabled, costs are checked before warmup and charged only after a successful teleport.

## Frontier Safety

When the worldborder module is enabled, teleport commands can be blocked from leaving or entering the frontier depending on worldborder settings. The bypass permission is intentionally separate so moderation staff can be granted it explicitly.

## Permissions

- `havennecessities.teleport.spawn`
- `havennecessities.teleport.home`
- `havennecessities.teleport.sethome`
- `havennecessities.teleport.delhome`
- `havennecessities.teleport.homes`
- `havennecessities.teleport.warp`
- `havennecessities.teleport.setwarp`
- `havennecessities.teleport.delwarp`
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
- `havennecessities.teleport.tppos`
