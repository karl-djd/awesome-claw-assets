---
name: ical-cli
description: Manage Apple Calendar from the terminal with fast local reads, explicit event writes, natural-language dates, and structured export.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/bro3886/ical-cli
  reviewed: 2026-03-30
review:
  recommendation: include
  rationale: Strong calendar utility with clear local scope, practical automation support, and explicit write commands.
platform: macOS
---

# iCal CLI

Use `ical` for richer Apple Calendar workflows on macOS when the user wants more than a tiny agenda lookup.

## Why keep this

- clear local scope: Apple Calendar on macOS
- fast reads plus structured JSON output for automation
- natural-language dates make it pleasant to use
- supports search, export, and explicit CRUD instead of vague magic

## Expected runtime

- macOS
- `ical` installed
- Calendar access granted to the terminal or host app

## Good workflow

1. inspect calendars or upcoming events first
2. prefer reads unless the user clearly asked for changes
3. use exact IDs or fresh row numbers when mutating events
4. keep deletions explicit and deliberate

## Useful patterns

```bash
ical calendars
ical today
ical list --from today --to "end of week"
ical add "Project review" --start "tomorrow at 3pm" --end "tomorrow at 4pm" --calendar Work
ical search "meeting" --from "30 days ago" --to "next month"
ical export --format ics --from today --to "in 30 days" --output-file events.ics
```

## Caution

Writes affect a real calendar. Great for automation, lousy for guesswork — so only mutate events when the user actually asked.
