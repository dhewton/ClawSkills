# ClawSkills

Built by **DannyBoy** — the **safe / secure / performance guy**.

ClawSkills is DannyBoy’s personal collection of OpenClaw skills and MCP-style integrations.

This repo exists for one reason: powerful automation should feel **inspiring**, **trustworthy**, and **production-safe**.

A lot of automation projects drift into one or more of these traps:
- clever but fragile
- fast but unsafe
- useful but undocumented
- powerful but impossible to review
- convenient until they hit real production pressure

ClawSkills is the opposite direction.

## What this repo stands for

Every skill in this collection should aim for the same standard:

- **Safe by default**
- **Secure in handling secrets and runtime state**
- **Performance-conscious and low-drift**
- **Operationally clear**
- **Reviewable before deployment**
- **Useful in the real world, not just impressive in a demo**

## Philosophy

This is not a random pile of experiments.

This is a curated operator-first collection for skills that DannyBoy has either:
- proven in his own environment
- refined into something trustworthy
- or is actively shaping into a polished public release

Some skills here may begin private, rough, or highly specific.
That is intentional.
They earn their way toward public release by being tested, hardened, and made clean enough to stand on their own.

## Collection structure

Each skill should eventually be self-contained and publication-ready, with:

- a clear README
- a `SKILL.md` or equivalent packaging doc when appropriate
- deployment notes
- validation notes
- strong guardrails
- no secrets committed to Git

## Current direction

The first published-quality skill in this collection is planned as:

- **Pepper Potts Google Calendar MCP**

That skill is built around:
- direct Google Calendar API usage
- Google-native reminders only
- approval-gated write actions
- clear runtime separation between code and secrets
- clean MCP transport behavior for OpenClaw

## Standard for public release

A skill should feel like it came from a serious operator.

That means it should make people feel:
- this is legitimate
- this is thoughtfully built
- this is safe to inspect
- this is professional enough to trust
- this was made by someone who understands production consequences

## Notes

- Secrets, OAuth tokens, and machine-specific runtime values do **not** belong in Git.
- Runtime truth and deployment truth should stay aligned.
- Safety is not cosmetic here. It is part of the product.

More skills will be added here over time.
