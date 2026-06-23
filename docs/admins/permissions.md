# Admin Permissions

This page highlights staff and admin permissions. Player permissions live in [Player Permissions](../players/permissions.md), and the full combined list lives in [Permission Index](../reference/permission-index.md).

- Admin root: `havennecessities.admin`
- Economy admin: `havennecessities.admin.balance`, `havennecessities.admin.bank`, `havennecessities.admin.serverbank`
- Events admin: `havennecessities.admin.events`
- Professions admin: `havennecessities.admin.professions`
- Storage admin: `havennecessities.admin.storage`
- Multi-Tool admin: `havennecessities.admin.toolbelt`, `havennecessities.admin.toolbelt.give`, `havennecessities.admin.toolbelt.clear`
- Spawners admin: `havennecessities.spawners.admin`, `havennecessities.spawners.give`, `havennecessities.spawners.inspect`, `havennecessities.spawners.modify`, `havennecessities.spawners.reload`, `havennecessities.spawners.bypass`
- ClaimsBridge admin: `havennecessities.admin.claimsbridge`, `havennecessities.admin.claimstorage`
- Worldborder admin: `havennecessities.admin.worldborder`
- Teleport setup/admin: `havennecessities.teleport.setspawn`, `havennecessities.teleport.setwarp`, `havennecessities.teleport.delwarp`, `havennecessities.teleport.tppos`, `havennecessities.teleport.claims.bypass`
- Server controls: `havennecessities.admin.time`, `weather`, `broadcast`, `gamemode`, `heal`, `feed`, `fly`, `speed`
- Moderation: `havennecessities.admin.kick`, `warn`, `ban`, `unban`, `mute`, `unmute`, `modhistory`
- Item tools: `havennecessities.admin.item`, `havennecessities.admin.item.unsafe`
- Chat/Discord staff: `havennecessities.admin.chat.discord`, `havennecessities.chat.channel.staff`, `havennecessities.chat.cooldown.bypass.market`

## Explicit Bypasses

Some bypasses default to false and should be granted intentionally:

- `havennecessities.worldborder.bypass.teleport-block`
- `havennecessities.worldborder.bypass.placement-block`
- `havennecessities.inventory.bypass.death-rules`
- `havennecessities.professions.bypass.death-penalty`
- `havennecessities.combat.bypass.teleport-block`
- `havennecessities.combat.bypass.flight-block`
- `havennecessities.combat.bypass.logout-penalty`
- `havennecessities.flight.bypass-charge`
- `havennecessities.sleep.bypass`
- `havennecessities.toolbelt.bypass.unlocks`
- `havennecessities.claimsbridge.bypass.frontier-claims`
- `havennecessities.claimsbridge.bypass.spawner-placement`
- `havennecessities.moderation.bypass.ban`
- `havennecessities.moderation.bypass.mute`
