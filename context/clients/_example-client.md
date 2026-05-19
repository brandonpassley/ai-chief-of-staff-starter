---
status: active  # active | dormant | churned | prospect
client: {{Client Name}}
started:
last_updated:
---

# {{Client Name}}

## How Claude Uses This File

Loaded when:
- This client comes up in a conversation, meeting, or debrief
- The user is preparing for a call with someone from this client
- The user mentions an action item involving this client
- During `/weekly-plan`, when allocating time / planning client work

Update this file via `/debrief` after client calls, or anytime new information surfaces.

---

## Snapshot

- **Status:** {{active / dormant / churned / prospect}}
- **Engagement type:** {{retainer / fixed-scope / hourly / one-off}}
- **Started:** {{Date}}
- **Renewal / End date:** {{Date or "ongoing"}}
- **MRR / Total contract value:** {{$X/mo or total}}
- **Industry:** {{e.g., B2B SaaS in marketing analytics}}
- **Their company size:** {{e.g., $5M ARR, 25 employees}}

## Why They're a Client

What problem you're solving. One paragraph. Specific.

> {{Example: "Acme had inconsistent content output despite a strong product. Their VP Marketing wanted to ship 3 LinkedIn posts/week + 1 thought-piece/month but kept getting sucked into other work. We installed our Content Operating System in March 2026. Now they ship reliably."}}

## Engagement Scope

What's in scope, what's out.

**In scope:**
- {{Deliverable 1}}
- {{Deliverable 2}}

**Out of scope (so we don't get pulled in):**
- {{Boundary 1}}
- {{Boundary 2}}

## Key Contacts

| Name | Role | Engagement style | Notes |
|---|---|---|---|
| {{Name}} | {{Title}} | {{Direct? Considered? Casual?}} | {{What they care about}} |

## Cadence

- **Weekly:** {{e.g., Friday status email; standing 30-min Mon}}
- **Monthly:** {{e.g., Strategy review on first Tuesday}}
- **Quarterly:** {{e.g., Renewal conversation, scope review}}

## Engagement History

Chronological log of significant moments.

| Date | What happened |
|---|---|
| {{YYYY-MM-DD}} | {{Started engagement at $X/mo retainer}} |
| {{YYYY-MM-DD}} | {{Scope addition — included Y for $Z}} |
| {{YYYY-MM-DD}} | {{Significant call / decision}} |

## Open Loops

What's currently pending with this client.

- ⏰ {{Open item — who owns it, by when}}
- ⏰ {{...}}

## Decision Log

Important decisions made during the engagement, for future reference.

| Date | Decision | Rationale |
|---|---|---|
| {{YYYY-MM-DD}} | {{Decision}} | {{Why}} |

## Risks / Watch-Outs

- {{Things that could turn this client south}}
- {{Specific landmines based on personality / past patterns}}

## Notes

Anything else worth capturing.

---

## Update Cadence

- After every client call → update via `/debrief`
- At each renewal → review status + decisions log
- When something material happens (scope change, key contact change, etc.) → update immediately

Tell Claude *"update [client name]"* anytime.
