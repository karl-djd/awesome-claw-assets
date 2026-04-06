---
name: n8n-ops
description: Create, inspect, debug, and test n8n workflows through the REST API with explicit confirmation around destructive or production-sensitive actions.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/samansalari/n8n-ops
  reviewed: 2026-04-06
review:
  recommendation: include with caveat
  rationale: Strong operational value for people who actually live in n8n, with concrete API guidance and decent guardrails, but it is environment-heavy and can touch real automation systems if used carelessly.
platform: n8n REST API / curl / jq / browser
---

# n8n Ops

Useful if you already run n8n and want the agent to stop fumbling around it.

## Why keep this

- real-world value for workflow creation, debugging, and execution tracing
- specific API paths and node rules make it more actionable than vague automation fluff
- includes decent safety language around delete, activate, and production changes
- good fit for staged workflow work where read-first, patch-second matters

## What I reviewed

- positioning is clear: operate an existing n8n instance via API
- dependency story is honest: `N8N_API_KEY`, `N8N_BASE_URL`, `curl`, `jq`
- destructive actions are called out for confirmation instead of being normalized
- no obvious credential exfiltration logic in the reviewed skill text

## Caveats

- only useful if the user already has n8n and API access set up
- high-impact environment: mistakes can modify live workflows
- needs adaptation to the host's actual tool stack and approval rules

## Notable risk level

Moderate. The skill itself is transparent, but the target system is live automation infrastructure, so operator discipline matters.
