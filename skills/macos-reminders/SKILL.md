---
name: macos-reminders
description: Create, list, and manage Apple Reminders on macOS through small local scripts and AppleScript.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/lucaperret/macos-reminders
  reviewed: 2026-03-20
review:
  recommendation: include
  rationale: Clear personal-productivity value, local-only behavior, and narrow permissions on a common macOS app.
platform: macOS
---

# macOS Reminders

Operate Apple Reminders from an agent using local scripts.

## Why keep this

- directly useful to normal Mac users
- clear boundary: Reminders only
- local automation, no cloud account required
- upstream handles relative dates carefully to avoid locale bugs

## Expected runtime

- macOS
- `osascript`
- `python3`
- Reminders.app

## Typical workflow

1. list reminder lists
2. choose the best list
3. send structured JSON to create the reminder
4. optionally list pending reminders back to the user

## Example commands

```bash
"$SKILL_DIR/scripts/reminders.sh" list-lists

echo '{"name":"Buy milk","offset_days":1,"hour":10}' | "$SKILL_DIR/scripts/reminders.sh" create-reminder

echo '{"list":"Shopping","include_completed":false}' | "$SKILL_DIR/scripts/reminders.sh" list-reminders
```

## Notes

- Best for requests like “remind me tomorrow at 2pm” or “add this to Shopping”.
- This is macOS-only by design.
- Since it touches a native app, it should stay tightly scoped to explicit reminder requests.
