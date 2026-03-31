---
name: claw-diary
description: Record agent activity into a local diary, then generate daily summaries, replay views, and lightweight stats.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/0xbeekeeper/claw-diary
  reviewed: 2026-03-31
review:
  recommendation: include-with-caveat
  rationale: Strong observability value and a small transparent wrapper, but it depends on an external npm package and includes a destructive clear command.
---

# Claw Diary

Use this when the user wants a local activity diary for an agent: daily summaries, replay-style review, search, and basic cost/activity stats.

## Why keep this

- real value for retrospectives and debugging
- clear scope instead of vague “memory magic” nonsense
- data stays in a dedicated local folder
- easy to explain to normal users

## Expected runtime

- `claw-diary` CLI installed
- writable `~/.claw-diary/` directory
- browser access for replay mode

## Good default workflow

1. Verify the CLI exists before suggesting commands.
2. Use summary or stats views first.
3. Treat replay mode as optional, not the default.
4. Confirm before any destructive cleanup.

## Useful patterns

```bash
claw-diary summarize today
claw-diary summarize week
claw-diary stats
claw-diary search refactor auth
claw-diary replay
```

## Caution

This skill is only as trustworthy as the installed `claw-diary` package. Review upgrades before blindly pulling new versions, and never run the clear command without explicit user confirmation.
