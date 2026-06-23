# Storage And Database

HavenNecessities currently uses SQLite.

## Active Backend

- SQLite is the active storage backend.
- The default database file is `havennecessities.db`.
- MySQL and MariaDB are planned for a later milestone but are not active.

## Data Areas

SQLite stores player wallets, banks, server bank state, cooldowns, homes, warps, moderation records, combat acknowledgements, professions progress, storage contents, claim storage, Haven spawner state, and other module data as enabled.

## Operational Notes

- Back up the database before risky config changes.
- Be careful when clearing storage or adjusting economy balances.
- Claim storage belongs to claims rather than individual players, so confirm the claim ID before purge or transfer actions.
- Haven spawner records track owner, mob, tier, and active state.
- Bank and server bank admin edits are recorded in audit history.
