# Discord Bridge

The Discord bridge is part of the chat module. Discord support is disabled by default and requires staff setup with a Discord bot, guild ID, and channel IDs.

## What It Does

- Relays configured Minecraft chat channels to Discord channels.
- Relays Discord messages back into Minecraft channels.
- Requires linked accounts for Discord-to-Minecraft chat by default.
- Can reward linked players with configured server commands.
- Can mark links inactive when players leave the Discord server.

## Linking Flow

1. Player runs `/discord link` in Minecraft.
2. The plugin gives the player a temporary code.
3. Player sends a DM to the bot with `link <code>` or `/link <code>`.
4. The link becomes active if the code is valid, not expired, and the Discord user is in the configured guild.

Players can also use:

- `/discord status` to check their link.
- `/discord unlink` to remove their link from Minecraft.
- `unlink` in a DM to remove their link from Discord.

## Linked Account Requirement

When linked accounts are required for inbound chat, Discord users must have active linked accounts before their Discord messages can appear in Minecraft. This keeps the bridge tied to known Minecraft players and makes moderation easier.

## Inactive Links

If a linked Discord user leaves the configured guild, the link is marked inactive. Inactive links cannot relay Discord chat into Minecraft.

The default inactive grace period is 30 days. If the player rejoins during that period, the link can reactivate. If configured reward removal is enabled, deactivate commands run when the link becomes inactive and activate commands run again when the link becomes active.

## Rewards

Link rewards are command based. A common setup is to add and remove a LuckPerms group:

```yaml
discord:
  linking:
    rewards:
      commands-on-activate:
        - "lp user <player> parent add linked"
      commands-on-deactivate:
        - "lp user <player> parent remove linked"
```

## Channel Mapping

Each chat channel can map to a Discord channel ID. For example, global, market, and staff chat can each relay to a different Discord channel. Channels that should not relay can keep their per-channel Discord setting disabled.

## Permissions

- `havennecessities.chat.discord.link`
- `havennecessities.admin.chat.discord`
