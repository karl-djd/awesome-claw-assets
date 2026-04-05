---
name: next-safe-action
description: Build typed Next.js server actions with schema validation, auth middleware, and structured error handling using next-safe-action.
source:
  upstream: https://github.com/TerminalSkills/skills/tree/main/skills/next-safe-action
  reviewed: 2026-04-05
review:
  recommendation: include with caveat
  rationale: Clear framework-specific value for modern Next.js apps, with transparent Zod-based validation guidance and no suspicious bundle contents, but it is intentionally niche and only fits projects already committed to Next.js server actions.
platform: Next.js 14+ / TypeScript / Zod
---

# Next Safe Action

Make server actions less flimsy than raw `FormData` hope-and-prayer code.

## Why keep this

- sharp scope: typed inputs, validation, middleware, and error handling for Next.js server actions
- examples are concrete enough to adapt into a real app instead of just hand-waving at the library
- useful for teams already living in App Router and Zod-heavy codebases
- reviewed upstream snapshot is doc-only, so the security surface is low

## Expected runtime

- Next.js 14+ project using server actions
- TypeScript plus `next-safe-action` and `zod`
- optional auth middleware integration such as NextAuth or a custom session layer

## Typical usage

```bash
npm install next-safe-action zod
```

## Bundle / safety notes

- reviewed upstream bundle is a single `SKILL.md`
- no scripts, binary payloads, browser hooks, or secret-handling steps in the reviewed snapshot
- main caveat is ecosystem fit: it is not a general web skill, only a good fit for specific Next.js stacks

## Caveat

- Good inclusion candidate, but keep it framed as a framework-specific skill rather than pretending it helps every frontend project.
