---
name: broken-link-checker
description: Verify external HTTP/HTTPS links with fast HEAD requests and structured JSON results.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/wanng-ide/broken-link-checker
  reviewed: 2026-03-28
review:
  recommendation: include
  rationale: Tiny, readable Node script with no dependencies or secret handling; useful for docs QA despite HEAD-method false-negative caveats.
---

# Broken Link Checker

Quick external-link validation for docs, READMEs, and reference lists.

## Why keep this

- obvious maintenance value
- tiny bundle, easy to audit in minutes
- outputs structured JSON instead of vague vibes
- no install tricks, no credentials, no persistence

## Expected runtime

- Node.js
- outbound HTTP/HTTPS access

## Good workflow

1. Pass one or more full URLs.
2. Review status codes and failures in the JSON output.
3. Re-test suspicious failures with `GET` or a browser when needed.
4. Fix or remove dead links only after confirming the target is actually broken.

## Notes

- The upstream script uses `HEAD`, so some servers will reject valid pages with 405 or other false negatives.
- It exits non-zero when any URL fails, which is handy for CI but worth calling out.
- The original usage path in upstream docs is slightly sloppy; keep the local invocation explicit.
