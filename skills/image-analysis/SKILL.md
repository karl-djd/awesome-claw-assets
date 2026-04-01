---
name: image-analysis
description: Extract a practical color palette and visual cues from an image. Use when the user wants dominant colors from a screenshot, mockup, or photo, or needs a fast palette to match an existing design.
source:
  upstream: TerminalSkills/skills
  reviewed: 2026-04-01
review:
  recommendation: include with caveat
  rationale: Useful and easy to explain, but the upstream bundle auto-installs npm dependencies on first run, so networked install behavior should be explicit.
---

# Image Analysis

Turn a screenshot into a usable palette instead of eyeballing hex values like a barbarian.

## Default workflow

1. Load the image file.
2. Extract dominant colors and rank them by prominence.
3. Label likely roles such as background, surface, accent, or text candidate.
4. Suggest where each color belongs in tokens, CSS vars, or theme config.

## Good uses

- extract colors from a screenshot
- match a prototype or mockup
- pull a quick palette from a photo or brand asset
- prep colors for later accessibility checks

## Good habits

- Report both hex values and approximate prominence.
- Separate dominant background colors from small accent colors.
- Pair this with contrast checking before recommending text colors.

## Caution

Extracted colors are descriptive, not automatically safe. A palette still needs human judgment and accessibility checks.
