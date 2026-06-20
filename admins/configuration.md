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

## MiniMessage

Messages use MiniMessage syntax. PlaceholderAPI is resolved only when the integration is available and the relevant module supports it.

## Important Defaults

- SQLite is the active storage backend.
- MySQL and MariaDB are planned but not active.
- Balance, bank, server bank, flight, inventory, worldborder, AFK, chat, custom message, combat, professions, and storage modules are opt-in.
- Teleport costs are disabled unless both balance and teleport cost charging are enabled.
