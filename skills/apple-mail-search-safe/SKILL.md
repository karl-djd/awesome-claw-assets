---
name: apple-mail-search-safe
description: Fast, read-only Apple Mail search on macOS with metadata and message-body lookup.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/gumadeiras/apple-mail-search-safe
  reviewed: 2026-03-21
review:
  recommendation: include
  rationale: Clear scope, local-only access, and a practical improvement over slow AppleScript mailbox searches.
platform: macOS
---

# Apple Mail Search Safe

Search local Apple Mail data quickly without turning the skill into a mail-sending agent.

## Why keep this

- clear purpose: search and inspect existing mail
- read-only behavior is easy to reason about
- useful for inbox triage, finding receipts, and locating old threads
- much faster than brute-force AppleScript mailbox iteration

## Expected runtime

- macOS
- Apple Mail.app local database
- `fruitmail` CLI (`apple-mail-search-cli`)

## Typical usage

```bash
fruitmail search --subject "invoice" --days 30 --unread
fruitmail sender "@amazon.com"
fruitmail unread --json
fruitmail body 94695
fruitmail open 94695
```

## Notes

- Best for requests like “find that receipt email” or “show unread messages from X”.
- This skill is intentionally read-only; sending mail should stay with dedicated mail tools.
- Since it reads from local Mail data, it fits personal macOS setups better than remote/shared environments.
