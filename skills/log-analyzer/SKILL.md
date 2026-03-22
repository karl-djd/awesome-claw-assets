---
name: log-analyzer
description: Analyze application and infrastructure logs to build a timeline, isolate root causes, and suggest concrete next steps.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/log-analyzer
  reviewed: 2026-03-22
review:
  recommendation: include
  rationale: Strong incident-debugging utility, no hidden automation, and good emphasis on chronology over guesswork.
---

# Log Analyzer

When logs are on fire, build the timeline first and find the first real failure instead of worshipping the loudest stack trace.

## Why keep this

- very practical for debugging incidents and outages
- handles common log formats without pretending every system is pretty JSON
- emphasizes causal ordering, correlation IDs, and first-error analysis
- recommends concrete follow-up steps instead of generic shrugging

## Expected runtime

- access to log files or command output
- standard shell text tools for filtering and sampling large files
- optional JSON-aware tooling when logs are structured

## Good default workflow

1. Identify the log format and incident time window.
2. Filter by time and severity.
3. Group recurring errors, but locate the first occurrence of each.
4. Correlate across services using timestamps and request IDs.
5. Return a short incident timeline, likely root cause, and next actions.

## Notes

- Start with the last few hundred lines on large files, then narrow further.
- WARN lines often matter; don't ignore them just because they are not screaming in uppercase.
- Be specific with timestamps, counts, and sample errors.
- Good fit for production debugging; low risk because it is analysis, not mutation.
