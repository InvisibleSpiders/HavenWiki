# Installation

HavenNecessities is a Paper plugin.

## Requirements

- Paper 26.1.2.
- Java 25.
- The built plugin jar from `build/libs/` or the GitHub Actions artifact.
- PlaceholderAPI, VaultUnlocked, and FancyDialogs are optional soft integrations.

## Basic Install

1. Place the HavenNecessities jar in the server `plugins` folder.
2. Start the server once to generate configuration files.
3. Review `plugins/HavenNecessities/config.yml`.
4. Enable desired modules under `plugins/HavenNecessities/modules/`.
5. Restart or use the configured reload flow where safe.

Most modules are disabled by default so servers can opt into features intentionally.
