# Storage And Database

HavenNecessities currently uses SQLite.

## Active Backend

- SQLite is the active storage backend.
- The default database file is `havennecessities.db`.
- MySQL and MariaDB are planned for a later milestone but are not active.

## Data Areas

SQLite stores player wallets, banks, server bank state, cooldowns, homes, warps, moderation records, combat acknowledgements, professions progress, storage contents, and other module data as enabled.

## Operational Notes

- Back up the database before risky config changes.
- Be careful when clearing storage or adjusting economy balances.
- Bank and server bank admin edits are recorded in audit history.
