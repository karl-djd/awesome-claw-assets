---
name: agent-hardening
description: Run synthetic prompt-injection and text-sanitization checks against an agent environment without touching local files or secrets.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/x1xhlol/agent-hardening
  reviewed: 2026-03-29
review:
  recommendation: include
  rationale: Narrow security scope, self-contained test payloads, and no hidden data access make it a strong safety-oriented addition.
---

# Agent Hardening

A lightweight self-test kit for catching basic injection and text-sanitization failures before they bite harder.

## Why keep this

- focused on a real problem: invisible characters, bidi spoofing, and hidden directives
- synthetic-only test inputs keep risk low
- no secret scraping, browser automation, or external account setup
- small enough to audit in one sitting

## Expected runtime

- Python 3
- a shell that can run short inline scripts

## Good default workflow

1. Run the included checks as written.
2. Treat failures as signals to improve sanitization or review guardrails.
3. Record what failed and what was fixed.
4. Re-run after prompt, parser, or tool-wrapper changes.

## Notes

- Good fit for safety smoke tests, not full red-team coverage.
- The skill is honest about its limits and avoids touching local memory, config, or user files.
- Pair it with broader review if the environment also executes shell, browser, or credential-heavy workflows.
