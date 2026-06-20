# Moderation

The server controls module includes UUID-based moderation commands.

## Commands

| Command | Description |
| --- | --- |
| `/admin kick <player> [reason]` | Kick an online player and record the action. |
| `/admin warn <player> [reason]` | Record a warning for a known player. |
| `/admin ban <player> [reason]` | Permanently ban a known player. |
| `/admin tempban <player> <duration> [reason]` | Temporarily ban a known player. |
| `/admin unban <player> [reason]` | Revoke active bans. |
| `/admin mute <player> [duration] [reason]` | Mute a known player. |
| `/admin unmute <player> [reason]` | Revoke active mutes. |
| `/admin modhistory <player> [page]` | View moderation history. |

Direct shortcuts are also available when server controls are enabled: `/kick`, `/warn`, `/ban`, `/tempban`, `/unban`, `/mute`, `/unmute`, and `/modhistory`.

## Bypasses

- `havennecessities.moderation.bypass.ban`
- `havennecessities.moderation.bypass.mute`

Muted players cannot chat unless they have the mute bypass permission.
