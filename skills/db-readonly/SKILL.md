---
name: db-readonly
description: Run safe read-only queries against PostgreSQL or MySQL for inspection, reporting, and troubleshooting.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/reed1898/db-readonly
  reviewed: 2026-03-21
review:
  recommendation: include
  rationale: Strong boundary control, practical ops value, and explicit refusal of mutating SQL makes it suitable for cautious use.
---

# DB Readonly

Inspect a database without turning a troubleshooting request into a schema accident.

## Why keep this

- clear promise: read only, no writes
- broadly useful for debugging, reporting, and quick data inspection
- explicit safety model blocks mutating SQL
- supports common environments: PostgreSQL and MySQL

## Expected runtime

- shell access
- PostgreSQL or MySQL client access
- connection env vars already configured
- helper script from the upstream bundle

## Typical usage

```bash
scripts/db_readonly.sh postgres "SELECT now();"
scripts/db_readonly.sh postgres "SELECT * FROM users LIMIT 100" --format csv --out /tmp/users.csv
scripts/db_readonly.sh mysql "SELECT NOW();"
```

## Notes

- Best for “count rows”, “show schema”, “sample recent records”, and “export a read-only report”.
- Exploratory queries should usually include `LIMIT`.
- If a task needs `INSERT`, `UPDATE`, `DELETE`, or schema changes, it no longer belongs to this skill.
