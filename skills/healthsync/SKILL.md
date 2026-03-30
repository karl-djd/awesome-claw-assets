---
name: healthsync
description: Query exported Apple Health data from a local SQLite database for trends, summaries, and read-only analysis.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/bro3886/healthsync
  reviewed: 2026-03-30
review:
  recommendation: include
  rationale: Clear read-only boundary, real everyday usefulness, and transparent local-only data access.
platform: macOS
---

# Healthsync

Use `healthsync` when the user wants to inspect Apple Health export data without touching the original database.

## Why keep this

- genuinely useful for personal health trend questions
- explicit read-only boundary
- local SQLite database is easy to inspect and reason about
- supports both quick CLI reads and deeper SQL summaries

## Expected runtime

- `healthsync` CLI installed
- Apple Health export already parsed into `~/.healthsync/healthsync.db`
- `sqlite3` optional for custom aggregation

## Good workflow

1. confirm the data exists and is recent enough
2. prefer `healthsync query` for common reads
3. use direct SQLite only for custom aggregation
4. never run write SQL against the database

## Useful patterns

```bash
healthsync query steps --total --from 2026-03-01
healthsync query heart-rate --limit 20
healthsync query sleep --format json --limit 30
sqlite3 ~/.healthsync/healthsync.db "SELECT date(start_date) day, ROUND(AVG(value),1) avg_hr FROM heart_rate GROUP BY day ORDER BY day DESC LIMIT 7"
```

## Caution

This skill should stay strictly read-only. If a command would modify the database, stop — that would be user-hostile and dumb.
