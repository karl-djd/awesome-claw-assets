---
name: focus-mode
description: Keep a user centered on one goal with gentle drift detection, parked tangents, and a simple persistent state file.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/savorgbot-exe/focus-mode
  reviewed: 2026-04-02
review:
  recommendation: include with caveat
  rationale: Clear and useful accountability workflow with lightweight local JSON state, but the passive drift-monitoring behavior needs careful tone so it stays helpful instead of naggy.
platform: cross-platform
---

# Focus Mode

Keep a conversation pinned to one concrete goal instead of wandering into seven side quests and a fresh tab spiral.

## Why keep this

- clear job: protect a focus session and gently steer back when the user drifts
- easy to explain and easy to demo
- local-only state in simple JSON files, so the bundle is transparent
- useful for ADHD-style workflows, deadline pushes, and accountability sessions

## Expected runtime

- any OpenClaw setup with file write access for local state
- persistent files under `~/.config/clawdbot-focus/`

## Typical usage

```text
/focus Ship the landing page
/focus tone strict
/focus
/focus done
```

## Bundle / safety notes

- upstream behavior is mostly documentation plus JSON state storage
- no obvious secret handling, browser hooks, or hidden network fetches in the reviewed bundle summary
- main product risk is UX, not security: over-eager drift detection can become annoying if the tone is too strict

## Caveat

- Best for users who explicitly opt into accountability. Do not force it on normal chats.
