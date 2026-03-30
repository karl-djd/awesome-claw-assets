---
name: gtasks-cli
description: Manage Google Tasks from a local CLI for list, create, complete, edit, delete, and export workflows when explicit OAuth setup already exists.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/bro3886/gtasks-cli
  reviewed: 2026-03-30
review:
  recommendation: include-with-caveat
  rationale: Useful task workflow with clear commands, but setup depends on user-managed Google OAuth credentials and prior authentication.
platform: cross-platform
---

# GTasks CLI

Use `gtasks` when the user specifically wants their Google Tasks, not a local checklist pretending to be one.

## Why keep this

- obvious practical value for people already using Google Tasks
- covers task lists plus task CRUD cleanly
- supports table, JSON, and CSV output for automation
- authentication burden is honest instead of hidden

## Expected runtime

- `gtasks` installed
- `GTASKS_CLIENT_ID` and `GTASKS_CLIENT_SECRET` set
- authenticated token already present or user ready to log in

## Good workflow

1. check installation and auth state first
2. list task lists before assuming names
3. use explicit list names for scripted actions
4. treat create, edit, complete, and delete as real account writes

## Useful patterns

```bash
gtasks tasklists view
gtasks tasks view -l "Work" --sort=due
gtasks tasks add -l "Work" -t "Finish report" -d "next friday"
gtasks tasks done 1 -l "Work"
gtasks tasks view -l "Work" --format=json
```

## Caution

This skill is fine once configured, but OAuth setup is the tax. Do not fake readiness if the binary, env vars, or login state are missing.
