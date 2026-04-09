# Validation — Pepper Potts Google Calendar MCP

This checklist exists so the skill earns trust before wider release.

## Validation goals

The skill should prove that it is:
- operationally clear
- safe around secrets
- stable under real runtime conditions
- accurate in read paths
- disciplined in write paths

## Preconditions

Before validating:
- local OAuth client file exists
- local OAuth token file exists
- token refresh works
- MCP bridge is reachable
- OpenClaw runtime is configured to see the bridge

## Acceptance checklist

### 1) Local auth material is present
- [ ] OAuth client file exists locally
- [ ] OAuth token file exists locally
- [ ] files are restricted to the runtime user
- [ ] no secret values are committed to Git

### 2) Bridge health is good
- [ ] MCP bridge health endpoint returns healthy
- [ ] no startup/auth errors in logs
- [ ] service remains stable after restart

### 3) Read paths work
- [ ] list calendars succeeds
- [ ] today's agenda succeeds
- [ ] date-range agenda succeeds
- [ ] free/busy lookup succeeds
- [ ] event search succeeds

### 4) Write paths are guarded
- [ ] create event is blocked without explicit approval
- [ ] update event is blocked without explicit approval
- [ ] delete event is blocked without explicit approval
- [ ] reminder changes are blocked without explicit approval

### 5) Approved writes actually work
- [ ] create event succeeds after explicit approval
- [ ] update event succeeds after explicit approval
- [ ] delete event succeeds after explicit approval
- [ ] reminder changes persist to Google Calendar

### 6) Reminder model is correct
- [ ] reminders are stored as Google Calendar event reminder fields
- [ ] no cron reminder system is introduced
- [ ] no local reminder sidecar is pretending to be calendar logic

### 7) Verification discipline holds
- [ ] write success is confirmed by readback or equivalent verification
- [ ] failures are reported honestly
- [ ] no fake success claims appear in operator flow

## Rollback triggers

Rollback or stop rollout if:
- auth material is missing or invalid
- token refresh fails repeatedly
- non-approved writes get through
- reminders depend on cron/timers
- tool visibility is unstable inside sessions
- logs show transport/protocol mismatch symptoms

## What not to do

- Do not commit OAuth secrets or token files
- Do not add cron-based reminders
- Do not widen write authority casually
- Do not claim production-readiness without evidence
- Do not let runtime truth drift too far from documentation

## Release bar

Pepper Potts Google Calendar MCP should only be treated as public-ready when DannyBoy is satisfied that it feels:
- safe
- secure
- performance-conscious
- professional
- worthy of attaching his name to
