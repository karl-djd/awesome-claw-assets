---
name: cross-validated-search
description: Source-backed web search and lightweight claim verification with explicit evidence reporting.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/wd041216-bit/openclaw-free-web-search
  reviewed: 2026-04-03
review:
  recommendation: include
  rationale: Useful verification-focused search workflow with explicit support/conflict framing, transparent CLI verbs, and no obvious shady behavior; setup is heavier than built-in web tools, but the positioning is honest.
---

# Cross-Validated Search

Use this when a task needs source-backed web search instead of vibe-based guessing: search the web, inspect pages, verify a concrete claim, and produce a small evidence report.

## Why keep this

- practical fact-checking workflow
- explicit support/conflict framing is more honest than fake certainty
- good fit for research, verification, and citation-heavy tasks
- transparent command model instead of magic black-box promises

## What I reviewed

- positioning is clear and specific
- workflow encourages citing sources instead of hand-waving
- dependency story is visible (`pip install cross-validated-search`)
- no obvious malicious or deceptive instructions in the reviewed skill file

## Notes

This is not a proof engine, and it says so. Good. That honesty is a point in its favor.

## Good uses

- recent factual lookups
- cross-checking a claim across multiple sources
- building a quick evidence summary with URLs
- surfacing source conflict instead of flattening disagreement

## Notable risk level

Low. Main tradeoff is setup overhead and heuristic verification quality, not safety.
