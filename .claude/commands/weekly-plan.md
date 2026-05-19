---
description: Plan the upcoming week — review Rocks, set MIT + Big 3, create time blocks on the calendar
---

# /weekly-plan — Build the Week

Run Sunday or Monday morning. Goal: walk away with a clear MIT, ranked focus areas, and time blocks already on the calendar.

## How Claude Uses This Command

The user types `/weekly-plan`. Walk them through a structured planning session that produces:
- An MIT (Most Important Thing) for the week
- Big 3 deliverables (controllable activity, not outcomes)
- Time blocks on the calendar (if Calendar MCP connected)
- Notion tasks for the week (if task tracker MCP connected)
- A saved plan file in `history/weekly-plan-[YYYY-MM-DD].md`

---

## Step 1 — Ingest (parallel)

Read in parallel:
- `CLAUDE.md` — identity, priorities, how the user works, coaching tone
- `context/rocks.md` — current quarterly Rocks
- `context/scorecard.md` — last week's actuals + this week's targets
- `context/annual-plan.md` — yearly OKRs for context
- `context/life-plan.md` — long-term destination check
- Most recent `history/weekly-wrap-*.md` (last week's wrap-up)
- Most recent `history/weekly-plan-*.md` (last week's plan, for cadence reference)

If no prior wrap-up exists, note at the top:
*"No wrap-up found for last week. Consider running `/weekly-wrap-up` first to ground the plan in what actually happened."*

Fetch in parallel (skip what isn't connected):
- This week's calendar — Google Calendar MCP
- Open tasks — Notion MCP or task tracker
- The user's separate "Time Blocks" calendar, if they use one

---

## Step 2 — Situational Review

### Scorecard Snapshot
Pull the current week's row from `context/scorecard.md`. Flag any blocking ❓ — but don't stop planning.

### Rock & OKR Review
For each active Rock in `context/rocks.md`:
- ✅ **On Track** — meaningful progress, will complete by quarter end
- ⚠️ **At Risk** — behind, needs a focused block this week
- ❌ **Off Track** — stalled, needs a decision (reset, descope, or kill)

State weeks remaining in the quarter and whether pace is sufficient.

### Open Loops
- All past-due tasks (with day count)
- This week's deadlines
- Backlog items with a due date this week → recommend promoting to ⏰ This Week

### Life Check
One line each:
- **[Primary business]** — pipeline, build progress, blockers
- **[Secondary business]** — under [time ceiling]? Any decisions needed?
- **Content** — cadence on track?
- **Personal** — workouts, finances, anything overdue?

---

## Step 3 — Coach's Take (forward-looking)

A real coaching section, not a summary. Reference `CLAUDE.md` "How I Want to Be Coached" for tone.

### Rock Status Table

| Rock | Status | Honest Read |
|---|---|---|
| Rock 1 | ✅/⚠️/❌ | [One sharp sentence — what's actually happening, with numbers] |

### Pattern Watch
Did any patterns repeat from recent weeks? Examples:
- "Build before selling"
- Specific habit slipping
- Time creep on a domain that should be capped
- Activity → outcome conversion breaking down

If the week was clean, name THAT too. Pattern-breaking is worth flagging.

### This Week's 3 Non-Negotiables
Three specific things — not themes, actual done states — that must happen this week. Ranked. If these three happen, the week wins.

Format: **1. [Specific deliverable]** — [why it's non-negotiable] — due [day]

### What to Ignore This Week
Explicitly name 2-4 things that should NOT get time this week. Give the user permission to say no.

### The Question to Carry
One sharp question that should follow the user through the week. Based on the biggest current gap between stated priority and actual behavior.

---

## Step 4 — Build the Plan

### MIT (Most Important Thing)
One sentence: *"This week wins if ___________."*
- Specific (name the deliverable)
- Completable by Friday
- Moves a Rock or generates revenue

### Big 3 (controllable activity only)

1. **[Activity-based deliverable]** — [why it's #1] — due [day]
2. **[Activity-based deliverable]** — [why it's #2] — due [day]
3. **[Activity-based deliverable]** — [why it's #3] — due [day]

**Critical rule:** Big 3 = controllable ACTIVITY ("send 100 cold touches"), NOT outcomes ("book 3 meetings"). Outcomes are downstream of activity.

**If the user proposes an outcome-shaped Big 3, push back:** *"That's an outcome, not an activity. What's the controllable activity that produces it?"*

### Time Available
Calculate gross hours minus known meetings. Show net deep work hours vs manager hours.

---

## Step 5 — Build Time Blocks (if Calendar MCP connected)

Ask: *"Which days are workout days?"* (typical: M/W/F or T/Th)

Then propose the week using these constraints:

| Time | What's happening |
|---|---|
| 6:00 – 8:00am | ⭐ Prime deep work (protect always) |
| 8:00 – 9:15am | Personal / kids / morning routine — skip |
| 9:15 – 11:00am | Deep work (non-workout day) OR workout |
| 11:00am – 12:30pm | Deep work continues |
| ~12:30 – 1:15pm | Lunch — skip |
| 1:15 – 5:30pm | Manager time (meetings, comms, admin) |

**Block colors (Google Calendar colorIds):**
- 🔴 Deep work / outreach → colorId 11 (Tomato)
- 🔵 Client work → colorId 9 (Blueberry)
- 🟡 Content → colorId 5 (Banana)
- 🟢 Other businesses / domains → colorId 2 (Sage)
- ⚫ Admin → colorId 8 (Graphite)

**Rules:**
- No block shorter than 90 minutes
- 6-8am = deep work only, always
- Never block over existing meetings
- Friday afternoon: weekly wrap-up + write next week's content (recurring pattern)

Format the proposed schedule, then ask: *"Looks good — want me to create these blocks?"*

If yes, create them on the user's "Time Blocks" calendar (or primary calendar if no separate one).

---

## Step 6 — Create Notion Tasks (if connected)

For each Big 3 item AND for recurring weekly activities (cold outreach, LinkedIn comments, content, etc.), create a Notion task with this week's due date.

Pattern: task on-screen + block on calendar = follow-through.

---

## Step 7 — Save Output

Save the full plan to `history/weekly-plan-[YYYY-MM-DD].md` where the date is this Monday.

Format:
```markdown
# Weekly Plan — Week of [Mon Date] – [Fri Date]

## MIT
[one sentence]

## Big 3
1. [deliverable] — [why] — due [day]
2. ...

## Coach's Take
[forward-looking accountability text]

## Rock Status
[per-Rock status]

## Open Loops
[past due + this week]

## Proposed Week
Mon: [blocks]
Tue: [blocks]
...

Total: Xhr deep | Xhr client | Xhr content | Xhr admin
```

---

## Step 8 — Post to Slack (if connected)

If Slack MCP is available, post the plan summary to the user's chief-of-staff channel. Plain text with emoji bullets.

---

## Step 9 — Always Create the Friday LI Posts Task

For users running a content cadence, always create a recurring Friday task: *"Write + queue 3 LI posts for next week."* This is the keystone content discipline — closes the loop alongside `/weekly-wrap-up`.

(If the user doesn't run a content cadence, skip this. But ask once during initial setup whether they want to.)

---

## Rules

- Revenue-first ranking. If it doesn't move money or a Rock, it goes last.
- Be opinionated. Don't present 10 equal options — tell the user what to do.
- If Rocks aren't defined yet, flag it and make *"Set Q[N] Rocks"* the MIT.
- Keep output scannable — bullets, no paragraphs.
- Big 3 = controllable activity. Push back on outcome-shaped Big 3 items.
