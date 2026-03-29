---
name: beeper
description: Search local Beeper chat history safely with read-only thread listing and full-text message lookup.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/krausefx/beeper
  reviewed: 2026-03-29
review:
  recommendation: include
  rationale: Clear read-only scope, practical chat-history search value, and minimal bundle risk.
platform: macOS, Linux
---

# Beeper

Search your local Beeper database without turning the skill into a message-sending gremlin.

## Why keep this

- clear scope: inspect existing chats, not send anything
- practical for finding old links, invoices, names, and context across unified inboxes
- upstream bundle is tiny and readable
- built around a dedicated CLI instead of fragile ad-hoc SQLite poking

## Expected runtime

- local Beeper Desktop data
- `beeper-cli` on `PATH`
- macOS or Linux

## Typical usage

```bash
beeper-cli threads list --days 7 --limit 50 --json
beeper-cli threads show --id "!abc123:beeper.local" --json
beeper-cli messages list --thread "!abc123:beeper.local" --limit 50 --json
beeper-cli search 'invoice' --limit 20 --json
beeper-cli search 'meeting' --context 6 --window 60m --json
```

## Notes

- Treat this as read-only local search.
- Prefer `--json` so results stay structured.
- Good fit for requests like “find that Telegram message with the tracking number” or “show recent chats mentioning the contract”.
- If the Beeper database lives somewhere unusual, point the CLI at it explicitly instead of guessing.
