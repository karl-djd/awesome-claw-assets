---
name: image-compare
description: Compare two images and quantify visual differences. Use when the user wants to check a design against an implementation, inspect regressions between screenshots, or generate a diff image for review.
source:
  upstream: TerminalSkills/skills
  reviewed: 2026-04-01
review:
  recommendation: include
  rationale: Narrow, practical visual-regression helper with understandable local dependencies and no obvious risky behavior.
---

# Image Compare

Use this when “looks basically the same” is too hand-wavy to trust.

## Default workflow

1. Load the two images.
2. Normalize dimensions if needed.
3. Compute mismatch percentage and generate a diff image.
4. Explain whether the change is trivial, noticeable, or substantial.

## Good uses

- compare a design mockup with a built page
- spot UI regressions between releases
- validate screenshots in a review workflow
- isolate where a layout drifted

## Good habits

- Keep viewport size consistent before comparing.
- Treat tiny diffs as possible anti-aliasing noise.
- Save the diff image so humans can inspect the change, not just a percentage.

## Caution

Pixel diffs are blunt instruments. They catch real regressions, but they also love false positives when rendering conditions change.
