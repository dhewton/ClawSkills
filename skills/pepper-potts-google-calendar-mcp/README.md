# Pepper Potts Google Calendar MCP

**Built by DannyBoy — the safe / secure / performance guy.**

Pepper Potts Google Calendar MCP is a safety-first Google Calendar integration for OpenClaw.

It is designed for operators who want calendar automation that feels:
- legitimate
- reviewable
- low-drift
- secure around secrets
- calm under production pressure

## Why this exists

A lot of calendar automation gets messy fast:
- wrapper-on-wrapper dependencies
- cron reminder hacks
- unclear write boundaries
- mystery auth handling
- secrets creeping into Git
- "works on my machine" deployment drift

This skill was built to go the other way.

## Design principles

- **Direct Google Calendar API access**
- **Google-native reminders only**
- **Approval-gated writes**
- **Runtime secrets stay local**
- **Operator-first deployment clarity**
- **Supergateway-compatible MCP transport**

## Capability model

Read paths should be straightforward:
- list calendars
- today agenda
- date-range agenda
- free/busy checks
- event search

Write paths should be deliberate:
- create event
- update event
- delete event
- update reminders

Write operations are meant to be approval-gated, not casually executed.

## Security posture

This skill is meant to feel trustworthy because it behaves like a real operator tool:
- no OAuth secrets in Git
- no token files in Git
- no cron reminder sidecar pretending to be calendar logic
- no fake success claims without readback/verification
- no sloppy runtime assumptions hidden in docs

## Current status

This entry is part of DannyBoy's growing ClawSkills collection.

It is being curated as a serious skill package rather than dumped out as a random experiment. Some pieces may begin as internal proving-ground work before they are polished for wider public release.

## Intended packaging

This skill is intended to live as a standalone public-quality repo once the collection is ready for broader release.

Until then, this directory acts as the curated skill landing area inside ClawSkills.
