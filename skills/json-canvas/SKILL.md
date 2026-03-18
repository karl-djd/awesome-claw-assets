---
name: json-canvas
description: Create and edit JSON Canvas files with nodes, edges, groups, positions, and connections. Use when working with .canvas files, Obsidian Canvas content, visual note maps, flowcharts, or structured canvas layouts.
---

# JSON Canvas

Work with `.canvas` files as structured JSON.

## Core workflow

1. Read and parse the existing canvas if one exists.
2. Keep the top-level structure valid: `nodes` and `edges`.
3. Generate unique IDs.
4. Validate every edge target before writing.
5. Re-check JSON validity after edits.

## Rules that matter

- Every node and edge ID must be unique.
- `fromNode` and `toNode` must reference real nodes.
- Use valid node types only.
- Keep layouts readable; avoid stacking everything into one ugly pile.

## When to read references

- Read `references/EXAMPLES.md` when the user wants a specific canvas pattern or layout example.

## Caution

A canvas file is still just JSON. If the JSON is broken, Obsidian will not reward creativity.
