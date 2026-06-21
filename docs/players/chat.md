# Chat

The chat module formats normal chat, optional specialty channels, tab names, item links, and player mentions. It is disabled by default until the server enables it.

## Channels

Global chat remains the normal channel. Players can keep typing normally and their messages use the configured global format.

Specialty channels can be reached with commands or shortcut prefixes:

| Channel | Default Commands | Default Shortcuts | Notes |
| --- | --- | --- | --- |
| Global | `/global <message>`, `/chat global <message>` | none | Normal unrestricted chat. |
| Market | `/market <message>`, `/chat market <message>` | `#`, `$` | Defaults to a 60 second cooldown. |
| Staff | `/staffchat <message>`, `/chat staff <message>` | `!`, `@` | Requires the configured staff channel permission. |

Shortcut examples:

```text
# Selling diamonds
$ Buying logs
! Staff message
```

## Item Links

Players with `havennecessities.chat.item-link` can type `[item]` or `[i]` in a message to link the item in their main hand.

Example:

```text
Selling my sword [item]
```

In Minecraft chat, the link uses the real item hover tooltip and can open an item preview. The tooltip preserves custom names, lore, enchantments, durability, custom model data, and other item metadata. Discord receives a plain text item summary instead of the Minecraft hover component.

If the player is not holding an item, the message is blocked with the configured empty-hand message. If the player lacks permission, the message is blocked with the configured no-permission message.

## Mentions

Players with `havennecessities.chat.mention` can mention online players by typing `@PlayerName`.

When the mentioned player is online, the mention can be highlighted in chat and the target can receive an action bar, title, and sound notification. Mentioning yourself is ignored by default.

## Tab List

The tab header, footer, and player name format are configured in the chat module. Header and footer values can be either a single MiniMessage string or a YAML list of lines.

Available built-in placeholders include:

- `<player>`
- `<display_name>`
- `<prefix>`
- `<pvp_marker>`
- `<online>`
- `<max>`

PlaceholderAPI values can be used in configured templates when PlaceholderAPI is installed.

## PvP Marker

When enabled, a player who kills another player in PvP can receive a temporary marker beside their name in chat and tab. The marker expires after the configured duration.

## Permissions

- `havennecessities.chat.use`
- `havennecessities.chat.item-link`
- `havennecessities.chat.mention`
- `havennecessities.chat.channel.staff`
- `havennecessities.chat.cooldown.bypass.market`
- `havennecessities.chat.discord.link`
