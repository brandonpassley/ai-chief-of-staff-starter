---
description: Suggest the next thing to add to your AI Chief of Staff based on where you are
---

# /grow — Next CoS Upgrade Suggestion

On-demand prompt: *"what should I add next to my CoS?"* Reads current state + `context/expansion-roadmap.md` and suggests the highest-leverage next addition.

## How Claude Uses This Command

The user types `/grow` when they want a deliberate suggestion. Read their current state, find the next high-impact item from `expansion-roadmap.md`, and surface it with context.

This command is ALSO called automatically at the end of `/weekly-wrap-up` (as the "Next CoS Upgrade" suggestion). Same logic; just different surface.

---

## Step 1 — Assess Current State

Read in parallel:
- `context/expansion-roadmap.md` — the ordered roadmap (✅ done / 📋 pending / 🚫 not applicable)
- `CLAUDE.md` — user's role, priorities, domains
- `context/rocks.md` — current Rocks (does any roadmap item directly serve a Rock?)
- `.mcp.json` (if exists) — which tools are connected
- `.claude/commands/` — which commands are defined
- Memory entries — has the user already declined any roadmap items?

---

## Step 2 — Pick the Next Item

Use this logic:

1. **Find the lowest-numbered Layer with unchecked items** in `expansion-roadmap.md`
2. **Within that layer, rank items by impact for THIS user's role** (from `CLAUDE.md`)
3. **Filter out anything the user previously declined** (check memory for *"declined to add X"* entries)
4. **Pick the top 1 — optionally show a runner-up**

If the user is at Layer 1 with multiple pieces missing: prioritize whichever unblocks daily rhythm first.
- `/day` is unblocked by Calendar + tasks
- `/weekly-plan` is unblocked by Rocks + scorecard
- `/debrief` is unblocked by a transcript source preference
- `/dashboard` is unblocked by Rocks + scorecard being populated

---

## Step 3 — Surface the Suggestion

Format:

```
## Your next CoS upgrade

**Add: [Item name]**

**Why now:** [1-2 sentences specific to the user — reference their Rocks, role,
or recent activity that makes THIS the right next move]

**What it unlocks:** [1-2 sentences — what new capability or savings this gives you]

**Time investment:** [DIY estimate, e.g., "15 minutes with Claude walking you through"]

**Want me to walk you through it?** Just say *"let's add [item]."*

---

*Runner-up: [next item] — say "show me the runner-up" to learn more.*
```

---

## Step 4 — If User Says "Yes, Let's Add It"

DON'T dump instructions. Walk them through the conversational install pattern:

1. Briefly explain what's about to happen (2-3 sentences)
2. Ask ONE setup question at a time (don't questionnaire them)
3. Make file edits as their answers come in
4. After install, run a test together (e.g., if adding Slack, post a test message)
5. Save a memory note: *"Brandon added [item] on [date] — uses it for [purpose]"*

When complete, update `context/expansion-roadmap.md` to mark the item ✅ done.

---

## Step 5 — If User Declines

If the user says *"not now"* or *"not interested in that"*:
- Don't push. Acknowledge the call.
- Save a memory entry: *"User declined [item] on [date] because [reason if given]"*
- This prevents `/grow` from re-suggesting the same thing repeatedly.

Offer the runner-up if it's meaningfully different.

---

## Step 6 — Soft CTA Footer

End every `/grow` output with this footer:

> ---
>
> *Stuck on any specific addition? Two paths to get unstuck:*
> *(a) ask me to walk you through it now*
> *(b) [book a 30-min Unstuck call with Brandon](https://cos.hyperedge.studio/book)*

The user can remove this from the file template if they don't want it.

---

## Rules

- Never suggest more than 1-2 items at a time
- Always tie the suggestion to the user's specific Rocks or role (read `CLAUDE.md` first)
- Respect *"no"* — don't re-suggest declined items
- Update `expansion-roadmap.md` checkboxes as items get added
- The runner-up should be qualitatively different from the main suggestion (not "add Slack" + "add Slack alerts")
- If everything in Layer 1 is done, jump to Layer 2. If everything in Layer 2 is done, congratulate them and move to Layer 3 with a noticeably bigger ask.
- If `CLAUDE.md` or `rocks.md` is empty, suggest filling those FIRST before anything else — they're foundational
