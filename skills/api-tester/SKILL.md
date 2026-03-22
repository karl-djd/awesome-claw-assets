---
name: api-tester
description: Test REST and GraphQL endpoints with explicit assertions, timing checks, and clear safety boundaries.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/api-tester
  reviewed: 2026-03-22
review:
  recommendation: include
  rationale: Clear scope, practical debugging value, and explicit warning against hitting production without confirmation.
---

# API Tester

Test APIs like an adult: send the request, verify the response, and do not casually poke production.

## Why keep this

- clear and common use case: endpoint checks, auth debugging, contract validation
- concrete workflow for REST and GraphQL
- pushes structured assertions instead of vague “looks fine” nonsense
- explicitly says to confirm before touching production

## Expected runtime

- shell access
- `curl` for quick checks
- optional Python 3.9+ with `requests` for more complex flows
- endpoint URL, method, headers, auth, and expected response details

## Good default workflow

1. Confirm whether the target is production, staging, or local.
2. Gather method, URL, headers, auth, body, and expected result.
3. Run the smallest useful request first.
4. Validate status, latency, content type, and important response fields.
5. Report pass/fail results clearly, with secrets masked.

## Notes

- Never hit production APIs without explicit user confirmation.
- Mask tokens, passwords, and API keys in output.
- Set timeouts so the agent does not hang forever on a dead endpoint.
- For multi-step flows, carry IDs and tokens forward intentionally instead of improvising.
