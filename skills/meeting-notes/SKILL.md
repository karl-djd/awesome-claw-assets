---
name: meeting-notes
description: Turn raw meeting notes or transcripts into clear summaries with decisions, action items, owners, and follow-ups.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/meeting-notes
  reviewed: 2026-04-08
review:
  recommendation: include
  rationale: Clear scope, low-risk bundle, and broadly useful for normal work without hidden automation or sketchy dependencies.
platform: cross-platform
---

# Meeting Notes

Convert messy transcripts, shorthand notes, or chat logs into something a team can actually use.

## Why keep this

- very easy to explain: summarize the meeting and pull out the work
- useful for normal users, not just engineers
- transparent bundle: documentation-only workflow with no hidden scripts
- strong default structure for decisions, owners, deadlines, and open questions

## Expected runtime

- any OpenClaw setup
- no special runtime beyond whatever text the user provides

## Good output shape

```markdown
# Meeting Summary: [title]

**Date:** [date]
**Attendees:** [names]

## Key decisions
- ...

## Action items
- Owner — task — due date

## Open questions
- ...

## Next steps
- ...
```

## Bundle / safety notes

- reviewed upstream bundle is doc-only (`SKILL.md`)
- no credential handling, shell automation, or network fetches
- main risk is factual sloppiness if the input transcript is bad, so summaries should keep uncertainty explicit

## Keep / skip call

Keep. It is simple, honest, and useful.
