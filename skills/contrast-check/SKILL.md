---
name: contrast-check
description: Check color contrast ratios for accessibility reviews. Use when the user wants to validate foreground/background pairs against WCAG AA or AAA thresholds, audit a palette, or catch unreadable UI colors before shipping.
source:
  upstream: TerminalSkills/skills
  reviewed: 2026-04-01
review:
  recommendation: include
  rationale: Clear accessibility utility with transparent local scripts and a narrow, beginner-friendly workflow.
---

# Contrast Check

Use this when color choices need proof instead of vibes.

## Default workflow

1. Gather the foreground/background hex pairs.
2. Compute contrast ratios.
3. Report AA and AAA pass/fail for normal and large text.
4. Flag failures and suggest darker or lighter replacements.

## Good uses

- audit a design palette
- verify button and text readability
- review UI screenshots after color extraction
- sanity-check rebrands before release

## Good habits

- Show the exact ratio, not just pass/fail.
- Call out whether the result only passes for large text.
- Keep decorative color checks separate from body-text checks.

## Caution

A color can look stylish and still fail basic readability. Pretty nonsense is still nonsense.
