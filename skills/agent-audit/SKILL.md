---
name: agent-audit
description: Audit an OpenClaw setup for model fit, cron spend, token waste, and likely savings without mutating config.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/sharbelayy/agent-audit
  reviewed: 2026-04-02
review:
  recommendation: include
  rationale: High-value read-only audit flow with explicit reporting, conservative recommendations, and clear usefulness for real OpenClaw operators.
platform: cross-platform
---

# Agent Audit

Read the setup, estimate where tokens and money are leaking, and point at the dumb parts before they keep billing.

## Why keep this

- strong practical value for anyone running multiple agents or cron jobs
- read-only posture is clearly stated
- recommendation model is transparent: task complexity, model tier, savings estimate, risk, confidence
- helpful for both home setups and more serious multi-agent deployments

## Expected runtime

- Python 3
- access to local OpenClaw config, cron metadata, and session history where available

## Typical usage

```bash
python3 scripts/audit.py --format summary
python3 scripts/audit.py --format markdown --output /tmp/agent-audit.md
python3 scripts/audit.py --dry-run
```

## Bundle / safety notes

- reviewed upstream description indicates local analysis and report generation only
- no automatic config rewrites; recommendations stay advisory
- risk is mainly estimate quality, not host compromise

## Review conclusion

- Good inclusion candidate for operators who care about cost hygiene and model-task fit.
