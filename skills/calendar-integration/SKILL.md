---
name: calendar-integration
description: Work with Google Calendar or Outlook calendar integrations for event creation, availability checks, recurring schedules, and free/busy workflows. Use when the user wants calendar API patterns, scheduling logic, booking flows, or event-management automation.
---

# Calendar Integration

Use this skill for calendar API work and scheduling logic.

## Default workflow

1. Identify the calendar system: Google or Outlook.
2. Confirm whether the task is read-only or write-capable.
3. Check availability before creating or moving events.
4. Be explicit about timezone handling.
5. Treat writes as user-facing actions that need clear intent.

## Good uses

- free/busy queries
- event creation flows
- recurring meeting logic
- booking and scheduling APIs
- sync or coordinator features

## Rules that matter

- Always specify timezone.
- Prefer availability checks before event creation.
- Keep attendee notifications in mind.
- Never silently create calendar events from vague intent.

## Caution

Calendar writes are social actions disguised as API calls. Double-booking someone because the code “worked” is still screwing up their day.
