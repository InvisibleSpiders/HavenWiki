# System Setup

Core settings live in `config.yml`. Module-specific settings live under `modules/`.

## Storage Backend

SQLite is the default active storage backend. It writes `havennecessities.db` in the plugin data folder.

MySQL and MariaDB sections are present with JDBC and HikariCP placeholders for a future storage backend, but servers should keep `storage.type: sqlite` until that backend is implemented.

## Timezone

Calendar-based systems can use the server JVM timezone or a configured ZoneId.

Set `time.timezone` in `config.yml` to a value such as `America/Edmonton` to pin event schedules, daily login interest payouts, and similar daily or scheduled systems. Bank interest can also override this under `modules/bank.yml`.

## Startup Failure Policy

`startup.module-failure-policy: isolate` keeps the plugin online if an optional module fails while enabling. The failed module is disabled and the rest of HavenNecessities continues.

Use `fail-plugin` only when you want strict all-or-nothing startup behavior.

## Security Notes

Live secrets should stay out of the repo and out of public screenshots. Keep Discord bot tokens, webhook URLs, database passwords, production databases, logs, and plugin runtime folders private.

