# backup

Sanitized OpenMario Postgres dump for local development.

- `openmario-sanitized-20261024.dump`: `pg_dump -Fc` of the public data (courses, sections, instructors, companies, positions, submissions, reviews). Taken 2026-10-24, before the latest term rescrape.
- Removed: all user/auth data (users, accounts, sessions, verifications, profiles) and emails, phone numbers and a named individual found in free-text fields.

Restore into a local dev database:

```bash
bun run dev:setup -- --restore path/to/openmario-sanitized-20261024.dump --seed-search
```
