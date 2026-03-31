---
name: a11y-auditor
description: Scan HTML and JSX for accessibility issues before review, then use the findings to prioritize obvious WCAG fixes.
source:
  upstream: https://github.com/clawdbot/skills/tree/main/skills/lxgicstudios/a11y-auditor
  reviewed: 2026-03-31
review:
  recommendation: include-with-caveat
  rationale: Practical pre-PR accessibility check with a simple workflow, but it depends on a third-party `npx` package and AI-generated suggestions should be verified.
---

# A11y Auditor

Run this before shipping or reviewing frontend code when you want a fast pass over obvious accessibility issues in HTML or JSX.

## Why keep this

- clear, common use case
- beginner-friendly one-command workflow
- good fit for pre-PR hygiene
- encourages concrete fixes instead of hand-wavy “we should care about a11y” talk

## Expected runtime

- Node.js 18+
- `npx`
- local HTML or JSX files to scan

## Good default workflow

1. Scan the smallest relevant directory first.
2. Triage high-severity issues before cosmetic cleanup.
3. Pair automated output with manual checks for keyboard and screen-reader behavior.
4. Treat generated fixes as suggestions, not gospel.

## Useful patterns

```bash
npx ai-a11y src/
npx ai-a11y src/components/Button.tsx
npx ai-a11y "src/**/*.jsx"
```

## Caution

Automated a11y tooling catches only part of the problem. Good smoke test, not a substitute for actual judgment.
