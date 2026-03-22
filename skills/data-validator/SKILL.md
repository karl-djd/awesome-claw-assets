---
name: data-validator
description: Validate CSV, JSON, and similar exports for schema issues, nulls, duplicates, outliers, and freshness problems.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/data-validator
  reviewed: 2026-03-22
review:
  recommendation: include
  rationale: Clear ETL-focused scope, actionable checks, and strong utility without unsafe side effects.
---

# Data Validator

Bad data rots quietly. This skill exists to catch it before dashboards, imports, and downstream jobs start lying with confidence.

## Why keep this

- strong real-world use case for ETL, imports, audits, and handoffs between teams
- validation categories are concrete: completeness, uniqueness, type consistency, range checks, freshness
- encourages profiling first, which is the difference between checking data and guessing at it
- low-risk, analysis-oriented workflow

## Expected runtime

- access to CSV, JSON, database exports, or query results
- shell tooling and, when needed, Python for richer profiling
- expected schema or business rules when contract validation matters

## Good default workflow

1. Profile the dataset first: shape, types, null rates, unique counts, date ranges.
2. Run targeted checks for required fields, duplicates, type drift, bad ranges, and stale data.
3. Separate hard failures from warnings.
4. Show sample bad rows so the user can actually fix something.
5. Suggest concrete remediation steps or follow-up queries.

## Notes

- Best for pre-import checks, pipeline QA, and sanity checks on exports.
- Outliers are warnings until there is a business rule saying otherwise.
- Schema drift is worth calling out even when the data still technically parses.
- Keep the report actionable; nobody needs a theatrical wall of percentages with no fix path.
