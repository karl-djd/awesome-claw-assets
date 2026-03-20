---
name: mermaid
description: Render Mermaid text diagrams into PNG, SVG, or PDF for docs, specs, and quick visual explanations.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/jarekbird/mermaid
  reviewed: 2026-03-20
review:
  recommendation: include
  rationale: High practical value, narrow scope, and a simple dependency story around Mermaid CLI.
---

# Mermaid

Turn Mermaid syntax into image or PDF output.

## Why keep this

- useful for architecture diagrams, flows, ER models, and timelines
- easy to explain to beginners
- output is deterministic and local once `mmdc` is available
- bundle is small and transparent

## Expected runtime

- Node.js
- `@mermaid-js/mermaid-cli` available as `mmdc`

## Typical usage

```bash
mmdc -i diagram.mmd -o diagram.png -t dark -b transparent -s 2
mmdc -i architecture.mmd -o architecture.svg
mmdc -i roadmap.mmd -o roadmap.pdf
```

## Good use cases

- generate diagrams for README files
- visualize login or payment flows
- sketch system architecture without opening a design tool
- render ER diagrams from database notes

## Notes

- Best results come from writing the `.mmd` file first, then rendering.
- For crisp images, use `-s 2` or higher.
- Keep this skill focused on rendering; diagram design still belongs in the prompt or draft text.
