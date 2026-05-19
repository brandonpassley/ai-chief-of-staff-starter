---
description: Process a call or meeting transcript into action items, tasks, and context updates
---

# /debrief — Process a Call

Run after any meeting or call where decisions were made, actions assigned, or context needs to flow into your CoS.

## How Claude Uses This Command

The user types `/debrief` (with or without arguments). Goal: turn a meeting transcript into structured outputs:
- Action items extracted + assigned
- Notion tasks created (if Notion MCP connected)
- Relevant context files updated (people.md, clients/, projects/)
- A clean summary delivered back to the user
- Optional: a Slack post or follow-up email draft

---

## Step 1 — Source the Transcript

If the user provides a transcript URL or pastes a transcript directly, use it.

If the user just runs `/debrief` without arguments, ask once:

> *Which transcript source should I pull from?*
>
> *— Fireflies (paste a meeting URL, or I'll pull from recent meetings)*
> *— Otter, Granola, Fathom, or similar — paste the transcript text*
> *— Manual paste — just drop the transcript directly into chat*
>
> *If this is your first debrief, what tool do you typically use for call transcripts? I'll remember for next time.*

**After the first use:** save the user's preferred source to memory (e.g., *"Brandon uses Fireflies for call transcripts"*). On subsequent `/debrief` runs, default to that source without asking again.

---

## Step 2 — Extract (Claude reads transcript)

Read the full transcript. Extract:

### Attendees
- Names, roles, companies. Cross-reference with `context/people.md` if available.

### Topics Covered
- Brief bullets — the main subjects discussed.

### Decisions Made
- Concrete decisions (do X, kill Y, hold on Z until date).
- Who decided + when applicable.

### Action Items
Each one MUST include:
- **Owner** (specific person, not "the team")
- **Action** (specific verb + object)
- **Due date** if mentioned
- **Dependencies** if any

### Open Questions
- Things left unresolved
- What needs follow-up

### Notable Quotes / Context
- Direct quotes capturing sentiment, positioning, or important framing
- Useful for future reference when the user is asked "what did they say about X?"

---

## Step 3 — Update Context Files

Based on what was discussed:

- **`context/people.md`** — if new people attended or you learned new things about existing contacts, update their entries
- **`context/clients/[client-name].md`** — if it was a client call, update their status, current scope, recent activity
- **`context/projects/[project-name].md`** — if it was a project call, update progress and blockers
- **`context/scorecard.md`** — if metrics were discussed (revenue, pipeline numbers), update relevant cells

Each update should be minimal and clearly attributed to the call date.

---

## Step 4 — Create Notion Tasks (if Notion MCP connected)

For each Action Item assigned to **the user**:
- Create a Notion task in their task tracker
- Set priority: 🔥 Today if due ≤24hrs, ⏰ This Week if due ≤7 days, 📋 Backlog otherwise
- Set project based on context (which client / business)
- Set due date if specified in the meeting
- Include a description with the call reference (date + attendees)

For action items assigned to **others**, optionally log them in the relevant client/project file as *"waiting on [person] for [thing] by [date]."*

---

## Step 5 — Output Summary to User

Render a clean summary in the chat:

```
## Debrief: [Meeting title] — [Date]

**Attendees:** [list]
**Duration:** [if known]

**Decisions:**
- [decision 1]
- [decision 2]

**Your action items (created in Notion):**
- ✅ [Task X created — due [date]]
- ✅ [Task Y created — due [date]]

**Their action items (logged in [file]):**
- Waiting on [person] for [thing] — by [date]

**Context files updated:**
- [file] — [what changed]

**Open questions to follow up on:**
- [question 1]
- [question 2]
```

---

## Step 6 — Optional: Draft Follow-Up

If the meeting suggests a follow-up message is needed (recap, next steps, proposal), offer:

> *Want me to draft a follow-up [email / Slack message / LinkedIn DM] capturing the recap and next steps?*

If yes, draft it in the user's voice (referencing `CLAUDE.md` tone preferences).

---

## Step 7 — Coach's Note (optional)

If the call reveals a coaching moment, surface it briefly:
- Did the user commit to something that conflicts with current Rocks?
- Did they miss a chance to push on price, scope, or next-step?
- Is there a pattern with this contact (e.g., *"Third call with X — no progress; ask explicitly if there's a fit"*)?

Keep this short (1-3 bullets) and only when there's real signal. Skip if the call was clean.

---

## Rules

- If transcript source isn't configured: ask once, save preference to memory, never ask again
- Don't create tasks the user doesn't own without explicit instruction
- Don't update context files for trivial mentions — only material new info
- Action items must be SPECIFIC — *"Brandon will follow up with Eric about pricing by Friday 5/22"* not *"Brandon to follow up"*
- When in doubt about action ownership or dates, ask the user to confirm before creating tasks
- If the transcript is long (> 30 min meeting), summarize aggressively — don't try to capture every line
