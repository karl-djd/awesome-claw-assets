---
name: excel-processor
description: Read, clean, transform, analyze, and export Excel or CSV data. Use when the user wants to inspect spreadsheets, clean columns, deduplicate rows, merge files, summarize tabular data, create pivot-style outputs, or export processed spreadsheet results.
---

# Excel Processor

Work with spreadsheets carefully and transparently.

## Default workflow

1. Load the file and inspect shape, columns, and types.
2. Report obvious data-quality issues.
3. Apply only the requested transformations.
4. Export to a new file unless overwrite is explicitly requested.

## Good uses

- clean messy rows
- deduplicate data
- split sheets
- aggregate and summarize
- convert between Excel and CSV
- prepare reports from tabular data

## Good habits

- Show row/column counts after load.
- Be explicit about date parsing.
- Preserve originals by default.
- Call out risky assumptions before mass edits.

## Caution

Spreadsheet work gets dangerous when people start “just fixing a few columns” on blind faith. Inspect first, mutate second.
