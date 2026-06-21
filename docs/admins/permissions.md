# Permissions

This page highlights major permission groups. For a fuller list, see [Permission Index](../reference/permission-index.md).

## Player Permission Groups

- Teleport: `havennecessities.teleport.*`
- Balance: `havennecessities.balance.*`
- Bank: `havennecessities.bank.*`
- Server bank: `havennecessities.serverbank.*`
- Flight: `havennecessities.flight.*`
- Storage: `havennecessities.storage.use`
- AFK: `havennecessities.afk.use`
- Chat: `havennecessities.chat.use`, item links, mentions, market/staff channels, Discord linking
- Custom messages: `havennecessities.custommessage.*`
- Professions: `havennecessities.professions.use`

## Staff Permission Groups

- Admin root: `havennecessities.admin`
- Economy admin: `havennecessities.admin.balance`, `havennecessities.admin.bank`, `havennecessities.admin.serverbank`
- Professions admin: `havennecessities.admin.professions`
- Storage admin: `havennecessities.admin.storage`
- Worldborder admin: `havennecessities.admin.worldborder`
- Server controls: `havennecessities.admin.time`, `weather`, `broadcast`, `gamemode`, `heal`, `feed`, `fly`, `speed`
- Moderation: `havennecessities.admin.kick`, `warn`, `ban`, `unban`, `mute`, `unmute`, `modhistory`
- Chat/Discord admin: `havennecessities.admin.chat.discord`

## Explicit Bypasses

Some bypasses default to false and should be granted intentionally:

- `havennecessities.worldborder.bypass.teleport-block`
- `havennecessities.worldborder.bypass.placement-block`
- `havennecessities.inventory.bypass.death-rules`
- `havennecessities.professions.bypass.death-penalty`
- `havennecessities.combat.bypass.teleport-block`
- `havennecessities.combat.bypass.flight-block`
- `havennecessities.combat.bypass.logout-penalty`
