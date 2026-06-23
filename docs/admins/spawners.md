# Spawners Admin

The spawners module is configured in `modules/spawners.yml` and is disabled by default.

## Admin Commands

| Command | Description |
| --- | --- |
| `/spawners give <player> <item-id> [amount]` | Give a configured Haven spawner item. |
| `/spawners inspect` | Inspect the placed Haven spawner you are looking at. |
| `/spawners setmob <mob>` | Change the inspected or targeted Haven spawner mob. |
| `/spawners setlevel <level>` | Change the Haven spawner tier. |
| `/spawners activate` | Mark a Haven spawner active. |
| `/spawners deactivate` | Mark a Haven spawner inactive. |
| `/spawners transfer <player>` | Transfer spawner ownership. |
| `/spawners reload` | View reload guidance for spawner config changes. |

## Example Flow

```text
/spawners give Steve spawner_core 4
/spawners inspect
/spawners setmob SKELETON
/spawners setlevel 2
```

## Configuration Notes

- `altar.mode: vanilla-material` lets any placed lodestone act as the attunement altar.
- `altar.mode: haven-item` requires the configured Haven altar item.
- `placement.max-per-chunk` and `placement.max-per-player` control spawner density.
- Mob entries can override global drop chances for higher-value mobs.
- Recipes can reference either vanilla materials or custom Haven item IDs.

## Permissions

- `havennecessities.spawners.admin`
- `havennecessities.spawners.give`
- `havennecessities.spawners.inspect`
- `havennecessities.spawners.modify`
- `havennecessities.spawners.reload`
- `havennecessities.spawners.bypass`

