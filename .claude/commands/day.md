---
description: Morning dashboard — yesterday's output, today's meetings, focus tasks, coach's pulse
---

# /day — Daily Plan

Run every morning. Goal: a fast, opinionated dashboard so the user knows exactly what's happening today before they sit down to work.

---

## How Claude Uses This Command

The user types `/day`. Produce a structured morning dashboard. Adapt gracefully to which MCP servers and context files exist — skip sections when data isn't available, but always end with the **Coach's Pulse** (it's the differentiator).

The output should be SCANNABLE (under 30 lines).

---

## Step 1 — Read Context (in parallel)

- `CLAUDE.md` — to know who the user is and how they work
- `context/rocks.md` — current quarterly Rocks (so today connects to bigger picture)
- `context/scorecard.md` — this week's metrics and targets
- `context/people.md` — names that might come up in today's meetings

If any of these are empty (status: `empty`), note it briefly at the top: *"Your [file] is still empty. Want to populate it?"*

---

## Step 2 — Fetch Today's Data (in parallel)

Run in parallel — skip any source that isn't configured:

- **Today's meetings** — Google Calendar MCP, if connected
- **Today's time blocks** — separate Time Blocks calendar, if user uses one
- **Yesterday's productivity** — Rize MCP or similar, if connected
- **Open tasks marked 🔥 Today priority** — Notion MCP or task tracker, if connected
- **Tasks completed yesterday + today** — Notion MCP, if connected

---

## Step 3 — Render the Dashboard

Use this structure:

### Header
e.g., `## Mon 5/18 — Q2 W7 Day 1`

### Yesterday's Output — IF AVAILABLE
One line max:
`Focus: Xh Ym · Total: Xh Ym · Score: XX/100 · Top: [category]`
Skip section if Rize/equivalent not connected.

### Today's Meetings
List chronologically. Prefix events with other attendees as 👥. Personal/routine events (kids, school drop-off, gym, lunch, dog walk) no special prefix.
If no meetings with others: "No external meetings today."

### Today's Time Blocks — IF EXIST
List the time blocks already on the calendar. Note any conflicts with meetings.
If no time blocks exist for today, skip this section and flag in Coach's Pulse: *"No time blocks for today — want to build them?"*

### Yesterday's Completions — IF ANY
Brief win list:
`✅ [Task name] · [Project]`
Skip if none.

### Today's Focus
List all tasks marked 🔥 Today priority. Count header: `**Today's Focus (N tasks)**`

### Open Tasks (next)
Show top 5-8 from: past-due (with day count) → ⏰ This Week. Skip Backlog unless past-due.

### Quick Pulse
One line: any blocker, deadline, or unusual thing happening today.

---

## Step 4 — Coach's Pulse (the differentiator)

After the dashboard, write **3-5 sharp bullets**. This is the COACHING layer. Reference:
- `CLAUDE.md` "How I Want to Be Coached" section for tone
- `context/rocks.md` for current Rock status (which are stalling?)
- Recent pattern in the user's last 3-5 days (drift to watch for?)

Rules:
- Reference the active Rocks and where they stand
- Call out repeating patterns (e.g., "Day 3 with no cold outreach")
- Name THE ONE THING that most needs to happen today — specific, not a theme
- If today's blocks don't reflect this week's top priority, flag it
- End with ONE sharp question or provocation
- Max 5 bullets. No paragraphs. No softening.

---

## Step 5 — Post to Slack — IF SLACK MCP CONNECTED

If Slack MCP is available, post a formatted summary to the user's chief-of-staff channel.

Include: yesterday's output, today's meetings, today's blocks, top tasks, coach's pulse. Plain text with emoji bullets.

If Slack isn't connected: skip this step. Optionally surface in dashboard: *"💡 Tip: Connect Slack to auto-post daily summaries. Ask: 'help me add Slack.'"*

---

## Rules

- Keep dashboard under 30 lines
- Bullets only — no paragraphs
- If it's **Monday**, flag at the top: *"Have you run `/weekly-plan` yet for this week?"*
- If it's **Friday**, flag at the top: *"Run `/weekly-wrap-up` this afternoon."*
- If it's a **weekend**, lighten the output: *"Saturday — what's the one personal thing on the list?"*
- Always end with Coach's Pulse — never skip
- If `CLAUDE.md` is empty: Coach's Pulse becomes *"Your CoS is fresh — let's populate CLAUDE.md before tomorrow's `/day` so I can coach against your real role."*
- If `rocks.md` is empty: Coach's Pulse includes *"Set up your Rocks this week so I can coach you against real targets."*

---

## When to update this file

Update this command file when:
- You add a new MCP server you want `/day` to read from
- You discover a recurring question your morning dashboard doesn't answer
- The user repeatedly asks for the same thing at the start of the day

Just tell Claude *"let's update /day to also include [X]"* and it'll edit this file.
