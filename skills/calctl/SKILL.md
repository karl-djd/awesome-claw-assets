---
name: calctl
description: Manage Apple Calendar events on macOS through a small CLI that uses fast reads and explicit local writes.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/rainbat/calctl
  reviewed: 2026-03-21
review:
  recommendation: include
  rationale: Narrow calendar scope, understandable local implementation, and straightforward usefulness for Mac users.
platform: macOS
---

# calctl

Use a local CLI to list calendars, inspect upcoming events, search titles, and add new Apple Calendar entries.

## Why keep this

- very clear boundary: Apple Calendar only
- useful everyday scheduling utility
- reads are fast via `icalBuddy`; writes stay explicit via AppleScript
- no cloud dependency beyond the calendars already configured on the Mac

## Expected runtime

- macOS
- `icalBuddy`
- Apple Calendar.app
- `calctl`

## Typical usage

```bash
calctl calendars
calctl show today
calctl show week --calendar Work
calctl search "meeting"
calctl add "Project review" --date 2026-03-24 --time 15:00 --end 16:00
```

## Notes

- Good fit for “what’s on my calendar today?” and “add an event tomorrow at 3pm”.
- Because it performs write actions, it should stay tied to explicit user intent.
- This is macOS-only by design.
