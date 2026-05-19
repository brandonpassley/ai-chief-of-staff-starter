---
description: Close out the previous week — fill scorecard, review Rocks, coach's accountability take
---

# /weekly-wrap-up — Close the Week

Run Friday afternoon (or Sunday morning before planning the next week). Account for what actually happened, fill missing scorecard data, give an honest coaching read, and save the wrap-up to `history/`.

## How Claude Uses This Command

The user types `/weekly-wrap-up`. Goal:
- Interactively fill any ❓ in the scorecard
- Render a structured analysis of the week (time, tasks, calendar, Rocks)
- Deliver a real coaching take with the headline verdict + one sharp question
- Save the wrap-up to `history/weekly-wrap-[YYYY-MM-DD].md`
- Suggest the next CoS upgrade

---

## Step 1 — Ingest (parallel)

Read:
- `CLAUDE.md`, `context/rocks.md`, `context/scorecard.md`, `context/annual-plan.md`, `context/life-plan.md`
- Most recent `history/weekly-plan-*.md` — what was committed this week
- Any active project / client files relevant to this week's work

Fetch in parallel (skip if not connected):
- Last week's productivity summary — Rize MCP or similar
- Last week's calendar events — Calendar MCP
- Tasks completed last week — Notion MCP
- Tasks not done — still open in Notion

---

## Step 2 — Scorecard Fill (INTERACTIVE — do not skip)

Pull the current week's row from `context/scorecard.md`. Find every ❓ or missing field. **Ask the user directly in chat — do NOT skip or assume.**

Present as a numbered list:

```
I need to fill in this week's scorecard. Answer these and I'll update the file:

1. [Metric 1] — what's the number?
2. [Metric 2] — what's the number?
3. [Metric 3] — ...
```

Wait for the user's answers. Then update `context/scorecard.md` with the new data. Mark cells confirmed; leave as ❓ anything the user says they don't know.

---

## Step 3 — Last Week Analysis

### Time Audit (if Rize / equivalent connected)
- Total tracked hours
- Focus hours + productivity score
- Time per domain (work / business / client / personal)
- Allocation vs target — was it aligned?

### Task Review
- **Completed this week** — list by day; group if 4+/day. Show project + priority.
- **Missed** — past-due tasks; days overdue. If high-priority tasks slipped while low-priority tasks completed, call it out.

### Calendar vs Reality
- Meetings that happened
- Did time blocks get honored?
- What unplanned thing ate time?

### Rock Progress
For each Rock in `context/rocks.md`:
- ✅ Progressed — what specifically moved (with numbers if possible)
- ➡️ No movement — expected or not?
- ❌ Regressed — what got worse

Update each Rock's status + last-updated date in `context/rocks.md`.

---

## Step 4 — Coach's Accountability Take

Full backward-looking review. Structured. No softening.

### Rock Status Table

| Rock | Last Week's Status | What Actually Happened |
|---|---|---|
| Rock 1 | ⚠️ At Risk | [One sentence with real numbers — not a label, what literally happened] |
| Rock 2 | | |

### Pattern Watch
Did any patterns from recent weeks repeat? Name them explicitly:
- "Build before selling" — time on building/planning instead of selling
- A habit cap getting breached (e.g., time-ceiling on secondary business)
- Content commitments slipping for the Nth week
- Any new pattern emerging

If the week was clean (no negative patterns), call THAT out too. Patterns breaking is worth naming.

### Time vs. Priority Gap
Where did time actually go vs. where it was supposed to go?
- State the target allocation
- State what the data shows
- Name the biggest misalignment in one sentence

### The Headline Verdict
One sentence: did this week move the ball or not? Be blunt.

Then 3-5 bullets with specific calls + numbers. Examples of the right tone:
- "You logged 14 hrs on client delivery. Target is 10. That's 40% over for the third week running — what specifically is your partner not owning that you're still doing?"
- "3 LinkedIn posts were on the plan. 1 went out. Content is the one Rock you have full control over, and it slipped again."
- "Fitness was the only habit that ran consistently — 3 workouts, on target. That's the floor, not the ceiling."

### One Sharp Question
Close with ONE question that should follow the user into next week's planning. Based on the biggest gap between stated priority and actual behavior.

---

## Step 5 — Save Output

Write the full wrap-up to `history/weekly-wrap-[YYYY-MM-DD].md` where the date is last Friday.

Format:
```markdown
# Weekly Wrap-Up — Week of [Mon Date] – [Fri Date]

**Generated:** [today's date]

## Scorecard (as filled)
[table of week's metrics]

## Time Audit
[time data]

## Tasks
**Completed:** [list]
**Missed:** [list with days overdue]

## Rock Progress
[per-Rock status]

## Coach's Take
[the accountability text]
```

---

## Step 6 — Update Context Files

After the wrap-up is saved:
- Update `context/rocks.md` with new status notes per Rock
- Update `context/scorecard.md` with the filled week row
- Update active project / client files if anything material happened this week

---

## Step 7 — Suggest Next CoS Upgrade (the /grow integration)

After the Coach's Take, add a final section:

> **Next CoS Upgrade:** Based on this week, the next thing I'd add to your CoS is **[item from `context/expansion-roadmap.md`]**. Here's why: [1-2 sentences specific to what happened this week]. Want me to walk you through it? Just ask.

This makes growth feel organic — the CoS literally tells the user what to add next.

(Logic: read `context/expansion-roadmap.md`, find the lowest-numbered Layer with unchecked items, pick the highest-impact for THIS user based on `CLAUDE.md` and what happened this week.)

---

## Step 8 — Prompt for /weekly-plan

After saving the wrap-up:

> *"Wrap-up done. Run `/weekly-plan` when you're ready to build next week."*

---

## Rules

- Do NOT skip the interactive scorecard fill — it's the whole point of this command
- Numbers, not vibes — "Logged X hrs on Y" beats "you worked a lot"
- If Rize / task data is incomplete, note it and ask the user to fill the gap manually
- The coach's take should make the user slightly uncomfortable. That's the point.
- Always end with the one sharp question
- If today is NOT Friday (e.g., user runs this on Saturday or Sunday), use yesterday's Friday as the wrap-up date
