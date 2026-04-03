---
name: redline
description: Check live Claude/OpenAI usage windows and apply simple pacing tiers before rate limits bite.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/wgj/redline
  reviewed: 2026-04-02
review:
  recommendation: include with caveat
  rationale: Useful guardrail for heavy OpenClaw users with explicit pacing tiers, but it depends on local auth state and provider-specific usage endpoints that may drift.
platform: macOS / OpenClaw auth profiles
---

# Redline

Watch your usage budget before the platform slaps your hands.

## Why keep this

- clear operator value for people who live near plan limits
- simple GREEN/YELLOW/ORANGE/RED pacing model is easy to adopt
- designed to slot into heartbeat workflows instead of needing a whole management stack
- practical for Codex and Claude-heavy personal setups

## Expected runtime

- macOS for Claude Keychain access
- OpenClaw auth profile for OpenAI/Codex usage checks
- local script execution

## Typical usage

```bash
scripts/claude-usage
scripts/claude-usage --json
scripts/openai-usage
scripts/openai-usage --json
```

## Bundle / safety notes

- upstream description centers on local token reads plus provider usage API calls
- no autonomous writes beyond optional heartbeat state storage
- caveat: depends on local credential locations and unofficial or change-prone usage surfaces

## Caveat

- Strong fit for power users; weaker fit for beginners who have not set up provider auth or heartbeat habits yet.
