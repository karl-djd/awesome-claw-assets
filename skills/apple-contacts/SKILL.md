---
name: apple-contacts
description: Look up names, phone numbers, and email addresses from macOS Contacts.app with simple local queries.
source:
  upstream: https://github.com/openclaw/skills/tree/main/skills/tyler6204/apple-contacts
  reviewed: 2026-04-09
review:
  recommendation: include with caveat
  rationale: Clear macOS utility and doc-only bundle, but it touches personal contact data, so scope and disclosure should stay tight.
platform: darwin
---

# Apple Contacts

Query macOS Contacts.app when the user wants to resolve a phone number, find a saved contact, or retrieve basic contact details locally.

## Why keep this

- concrete everyday use case
- dead-simple command surface through AppleScript
- read-oriented workflow with no hidden installers in the reviewed bundle
- good fit for personal assistant setups on macOS

## What I reviewed

- upstream bundle is doc-only (`SKILL.md` + `_meta.json`)
- scope is narrow: local Contacts lookups only
- commands are explicit and easy to audit
- no credential harvesting, binaries, or opaque network fetches in the bundle

## Caveat

Contact data is personal. Use the smallest query that solves the job, avoid dumping the whole address book unless asked, and treat names / phones / emails as sensitive output.

## Good uses

- resolve a caller or sender from a known phone number
- search saved contacts by partial name
- fetch one contact's phones and emails when the user explicitly asks

## Notable risk level

Low-to-moderate. Operationally simple, but it reads private local address-book data.