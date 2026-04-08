---
name: tech-debt-analyzer
description: Find technical debt worth fixing by combining code smells with git history, churn, and bug signals instead of dumping a useless wall of TODOs.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/tech-debt-analyzer
  reviewed: 2026-04-08
review:
  recommendation: include with caveat
  rationale: Strong framing and a genuinely useful prioritization model, but it is best for repositories with decent git history and can overstate precision if the scoring is treated like math from heaven.
platform: cross-platform
---

# Tech Debt Analyzer

Not all debt hurts equally. This one tries to separate ugly-but-harmless code from the stuff actively wasting engineering time.

## Why keep this

- better than generic "find TODOs" fluff because it uses churn and bug history too
- useful for refactor planning, maintainability reviews, and engineering triage
- transparent workflow built from standard repo inspection commands
- narrow enough to explain, broad enough to matter

## Expected runtime

- a git repository with meaningful history
- optional package-manager tooling if dependency drift checks are included

## Review notes

- the core idea is solid: rank debt by impact, not just existence
- output should be framed as a prioritization aid, not objective truth
- weak or shallow git history will reduce signal quality
- results should cite the evidence used: hotspots, churn, fix frequency, or complexity clues

## Bundle / safety notes

- reviewed upstream bundle is documentation-only (`SKILL.md`)
- no hidden automation, credential scraping, or network-heavy behavior in the bundle itself
- practical risk is low; the main failure mode is false confidence from oversimplified scoring

## Keep / skip call

Keep with caveat. Worth including because it pushes agents toward evidence-backed refactor advice instead of cargo-cult cleanup.
