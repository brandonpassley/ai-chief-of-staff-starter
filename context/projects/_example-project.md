---
status: in-progress  # planning | in-progress | shipped | paused | cancelled
project: {{Project Name}}
started:
target_ship:
last_updated:
---

# {{Project Name}}

## How Claude Uses This File

Loaded when:
- This project comes up in conversation, planning, or `/weekly-wrap-up`
- A meeting / call references it
- The user is allocating time during `/weekly-plan`
- A decision needs project context

Update via `/debrief` after project calls, or anytime status changes.

---

## Snapshot

- **Status:** {{planning / in-progress / shipped / paused / cancelled}}
- **Owner:** {{Person — usually you, but could be a teammate}}
- **Started:** {{Date}}
- **Target ship date:** {{Date}}
- **Client / Stakeholder:** {{Name + link to `context/clients/[name].md` if applicable}}
- **Budget:** {{Fixed fee, hourly cap, or "n/a"}}

## What This Project Is

One paragraph. Specific. The strategic note: why this matters and what changes when it ships.

> {{Example: "A custom internal tool for [Client]. Phase 1 ships the core ingestion + AI extraction + an internal management view. Strategic context: largest single engagement to date; successful delivery deepens the [Partner] relationship and produces case-study fuel for our productized offer."}}

## Scope

**In scope:**
- {{Deliverable 1}}
- {{Deliverable 2}}
- {{Deliverable 3}}

**Out of scope (explicitly):**
- {{Anything that might creep in but won't}}
- {{...}}

## Lane Boundaries (if multiple parties)

If multiple people / companies are involved, who owns what.

| Person / Party | What they own |
|---|---|
| {{You}} | {{Your lane}} |
| {{Collaborator 1}} | {{Their lane}} |

## Status Snapshot

What's actually shipped vs. what's still in flight. Updated weekly.

- ✅ {{Done}}
- 🟡 {{In progress}}
- 🔴 {{Blocked or waiting}}
- 📋 {{Not started}}

## Active Waiting-On

What's blocking forward progress, and who owes you.

- {{Person}}: {{What you need from them}}
- {{...}}

## Open Decisions

Decisions still being worked. Each one slated for resolution by a specific date.

- {{Decision needed}} — owner: {{Person}} — by: {{Date}}

## Risk Flags

Risks to the project. Prioritized.

1. **{{Risk 1}}** — {{What could go wrong + mitigation}}
2. **{{Risk 2}}** — {{...}}

## Decision Log

Important decisions, for future reference.

| Date | Decision | Rationale |
|---|---|---|
| {{YYYY-MM-DD}} | {{Decision}} | {{Why}} |

## Weekly Tracker

Filled in at each Friday wrap-up.

### Week of {{Date}}
- **Planned:** {{What was on this week's plan for this project}}
- **Done:** {{What shipped}}
- **Blockers:** {{Anything that came up}}
- **Slip vs baseline:** {{Days behind or ahead}}

---

## Update Cadence

- **Weekly Friday wrap-up** — update the Weekly Tracker section
- **After any project meeting** — `/debrief` updates status + open loops
- **When scope changes** — log it in the Decision Log + update Scope section
- **When risks materialize** — flag in real-time

Tell Claude *"update [project name]"* anytime.
