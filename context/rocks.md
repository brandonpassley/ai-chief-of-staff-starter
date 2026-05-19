---
status: empty  # empty | partial | complete
quarter:        # e.g., Q2-2026
last_updated:
last_reviewed:
---

# Quarterly Rocks

## How Claude Uses This File

Holds the user's **current quarterly Rocks** (EOS framework). Loaded when:
- Running `/weekly-plan` — Rocks shape the week's MIT and Big 3
- Running `/weekly-wrap-up` — every Rock gets a status update
- The user makes a tradeoff or commitment — does this serve a Rock?
- Mid-quarter checkpoint — hard review

When this file is empty (new quarter) or stale (>14 days since update), proactively run the Rock-setting conversation. Use the standards below; **push back on weak Rocks** before they get written down.

## What Makes a Good Rock

A Rock is a **90-day specific outcome** that moves your business forward. EOS framework: 3-7 Rocks per quarter. Each Rock has:

- **A specific outcome** — not an activity, not a theme
- **An owner** — one person, not "the team"
- **A measurable OKR** — you'll know clearly when it's hit or missed
- **A done state** — concrete description of "complete"
- **Weekly leading indicators** — *controllable activity* you can track each Friday
- **A decision gate** — a mid-quarter checkpoint date + criteria

## Coaching Standards (push back when...)

Common Rock mistakes to coach against:

- **Outcomes too vague:** "close more clients" → ask: how many, what price point, by when, what's the bottleneck?
- **Outcome targets as weekly indicators:** "Book 3 calls this week" isn't controllable. "Send 100 cold touches" is. Rocks can be outcome-shaped; **leading indicators MUST be controllable activity.**
- **Multiple Rocks competing for same time/owner:** ask which is most important — kill the rest or move to next quarter
- **No decision gate:** ask "when will you know if this is working?" Set a date.
- **Pretend Rocks:** if it's just "keep doing what we're doing," it's not a Rock. Rocks are deliberate stretches.
- **Avoidance of hard truths:** if last quarter's Rock missed badly and they're proposing the same one again, push back. What's actually changed?

**Equally important:** help the user explicitly name **what's NOT a Rock** — things competing for time that didn't make the cut. The cut list matters as much as the Rocks themselves.

---

## Quarter: Q{{N}} {{YEAR}} ({{start date}} – {{end date}}) — Week {{X}} of 13

**Quarter thesis:** {{One sentence: what does this quarter need to accomplish for the business?}}

**The constraint:** {{What's the bottleneck? What's the rare resource being stewarded? Time? Cash? Founder's attention? Sales focus?}}

---

### Rock 1: {{NAME}}

- **Owner:** {{Person}}
- **OKR:** {{Specific measurable target by end of quarter}}

**Done state ({{end of quarter}}):**
- {{Concrete description of what "done" looks like — bullets}}
- {{...}}

**Weekly leading indicators (track each Friday):**
- {{Controllable activity #1 — what you'll DO weekly to move this}}
- {{Controllable activity #2}}

**Decision gate — {{date around week 6-7}}:** {{Criteria — when will you know if this is working? What triggers a reset?}}

**Hard rules:**
- {{Anything off-limits, non-negotiable, or excluded from this Rock's scope}}

**Status:** {{✅ On Track / ⚠️ At Risk / ❌ Off Track}}
**Last updated:** {{Date}}

---

### Rock 2: {{NAME}}

[Same structure as Rock 1]

---

### Rock 3: {{NAME}}

[Same structure]

---

[Most quarters have 3-5 Rocks. 7+ usually means you haven't picked. Add more sections only if truly needed.]

---

## What Got Cut This Quarter (do not let these sneak back in)

- {{Thing that's not a Rock this quarter — and why}}
- {{Another}}
- {{...}}

**The filter:** Does this serve a Rock? If no → it doesn't happen this quarter.

---

## Mid-Quarter Checkpoint — {{date around end of week 6}}

Hard review. No softening.

1. {{Critical question 1 — usually tied to Rock 1's OKR}}
2. {{Critical question 2 — Rock 2's OKR}}
3. {{Critical question 3 — Rock 3's OKR}}
4. {{Personal cadence check — workouts, reviews, etc.}}

**If 2+ are red → cut a Rock entirely and concentrate fire.**

---

## Previous Quarter Retrospective

*Populated at the end of each quarter — what hit, what missed, patterns to carry forward.*

### Overall Grade: {{A / B / C / D / F}}

{{One paragraph honest read on the quarter}}

### Rock Results

| Rock | Status | Key Number |
|---|---|---|
| {{Rock 1}} | {{✅ Hit / ⚠️ Partial / ❌ Miss}} | {{Actual vs target}} |
| {{Rock 2}} | | |
| {{Rock 3}} | | |

### Patterns Named (carry into next quarter)
1. {{Pattern observed}}
2. {{...}}
3. {{...}}

---

## Review Cadence

- **Every Friday `/weekly-wrap-up`** — update Rock statuses; flag drift
- **Mid-quarter checkpoint** — hard review at decision gate
- **End of quarter** — full retrospective + Rocks reset for next quarter

To update: tell Claude *"let's review my Rocks"* anytime.
