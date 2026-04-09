---
name: pepper-potts-google-calendar-mcp
description: Safety-first Google Calendar MCP for OpenClaw with direct API access, Google-native reminders, approval-gated writes, and operator-first deployment discipline.
---

# Pepper Potts Google Calendar MCP

Pepper Potts Google Calendar MCP is a production-minded Google Calendar skill package for OpenClaw.

## Focus

This skill is for operators who want:
- direct Google Calendar API access
- Google-native reminders only
- explicit approval before writes
- local-only secret handling
- low-drift MCP deployment behind supergateway

## Guardrails

- No OAuth secrets or token files in Git
- No cron reminder hacks
- No fake success claims without verification
- Write operations should be explicit and approval-gated
- Runtime documentation should stay aligned with real deployment behavior

## Intended capability set

Read operations:
- list calendars
- today agenda
- range agenda
- search events
- free/busy lookup

Write operations:
- create event
- update event
- delete event
- change event reminders

## Approval model

Write actions are intended to require an explicit approval contract rather than a vague boolean. This keeps the skill aligned with operator-grade review and human confirmation patterns.

## Runtime expectations

Expected local runtime inputs:
- Google OAuth client file
- Google OAuth token file
- MCP bridge process behind supergateway

These remain local runtime assets and are never part of Git.

## Status inside ClawSkills

This skill is currently part of DannyBoy's private/proving collection. It is being shaped toward a public-quality release standard.
