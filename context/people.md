---
status: empty  # empty | partial | complete
last_updated:
---

# People

## How Claude Uses This File

The **relationships layer** — your relationship intelligence about specific individuals. Loaded when:
- A name comes up in a meeting, debrief, or conversation
- The user is prepping for a call (`/prep` style command, when built)
- The user is drafting outreach (LinkedIn DM, email, etc.)
- During `/debrief`, to update entries with new info

This file is for **named individuals**, not companies or generic categories.

## Where Things Belong (the architecture)

| Layer | Goes Here | Example |
|---|---|---|
| Named individuals (engagement style, prefs, what they care about) | `context/people.md` | A key partner, advisor, or recurring contact |
| Companies you sell to or partner with | `context/clients/` or company entries in Notion | Acme Corp, WidgetCo |
| Specific engagements or product builds | `context/projects/` | A specific client engagement or product build |
| Pipeline data (status, deal value, last touch) | Notion or your CRM | All deal-tracking |

**Rule of thumb:** if it's about *how to engage someone*, it goes here. If it's about *what stage their deal is in*, it goes in Notion.

## Coaching Standards (what makes a useful entry)

A strong people entry includes:
- **Role + company** — current
- **Relationship type** — friend / partner / client / prospect / mentor / etc.
- **How we met** — context for future reference
- **Engagement style** — direct? Socratic? Wants details? Prefers brevity?
- **What they care about** — their goals, current priorities, pet projects
- **What NOT to do** — things to avoid (e.g., never pitch on first call, never email after 5pm)
- **Last touch + how** — kept fresh via `/debrief` updates

When the user mentions a new person worth tracking, ask if it should go here:
*"Want me to add [name] to your people file? I'll ask 3-5 quick questions."*

---

## Entry Template

```markdown
### {{Name}}
- **Role:** {{Title @ Company}}
- **Relationship:** {{friend / partner / client / prospect / mentor / etc.}}
- **How we met:** {{Context}}
- **Engagement style:** {{Direct? Considered? What works?}}
- **What they care about:** {{Current priorities, projects, interests}}
- **Avoid:** {{Things to NOT do — timing, topics, framing}}
- **Last touch:** {{Date + how — call, DM, email}}
- **Open loops:** {{Anything pending between you}}
```

---

## My People

[Claude: populate this section through conversation. Add entries as people come up. Update existing entries via `/debrief` or natural conversation about a call.]

---

## Review Cadence

- **During `/debrief`** — update entries based on what was discussed
- **At quarterly review** — prune entries for relationships that have gone cold or are no longer relevant
- **On-demand** — ask Claude "let's update [person]" anytime

To add or update: tell Claude *"let's add [name] to my people file"* or *"update [name] — they just told me X."*
