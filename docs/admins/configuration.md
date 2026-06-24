# Configuration

HavenNecessities stores global settings, messages, permissions references, and module settings in separate files.

## Main Files

| File | Purpose |
| --- | --- |
| `config.yml` | Storage, integrations, and diagnostics. |
| `messages.yml` | MiniMessage-formatted player text. |
| `permissions.yml` | Permission reference. |
| `modules/*.yml` | Per-module settings and startup switches. |

Each module file includes an `enabled` switch.

For practical snippets and explanations of the most important customization keys, see [Config Examples](config-examples.md).

## MiniMessage

Messages use MiniMessage syntax. PlaceholderAPI is resolved only when the integration is available and the relevant module supports it.

## Important Defaults

- SQLite is the active storage backend.
- MySQL and MariaDB are planned but not active.
- Balance, teleport, chat, combat, and Multi-Tool are enabled by default in the current config.
- Bank, server bank, events, inventory, worldborder, cosmetics, professions, storage, rewards, ClaimsBridge, profile, and spawners are opt-in.
- Teleport costs are disabled unless both balance and teleport cost charging are enabled.
