---
name: domain-checker
description: Check whether a domain is likely available by cross-checking `whois` output with DNS nameserver and A-record signals.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/blueyi/domain-checker
  reviewed: 2026-03-28
review:
  recommendation: include
  rationale: Clear everyday use case, narrow shell-only scope, and transparent availability heuristics without sketchy network writes or hidden installs.
---

# Domain Checker

Check domain availability without trusting random registrar pages that love making a mess of the truth.

## Why keep this

- practical for naming, brand checks, and quick domain triage
- easy to explain: `whois` plus DNS cross-checks
- low bundle complexity
- no credentials, daemons, or persistent services

## Expected runtime

- shell access
- `whois`
- `dig`
- outbound DNS / whois access

## Good workflow

1. Gather one or more candidate domains.
2. Run the bundled checker in batch when possible.
3. Treat `AVAILABLE` as a strong signal, not a purchase guarantee.
4. Tell the user to verify final price and checkout status at a registrar before committing to a name.

## Notes

- `.ai` and some other TLDs can return sparse whois output, so DNS cross-checking matters.
- Premium or aftermarket domains may still cost money even when registration data looks open.
- For large batches, throttle requests instead of hammering whois servers like a fool.
