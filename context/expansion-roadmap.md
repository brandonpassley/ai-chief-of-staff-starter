---
status: complete
last_updated: 2026-05-18
---

# Expansion Roadmap — What to Add to Your AI Chief of Staff

## How Claude Uses This File

This file maps the journey from a Layer 1 Personal CoS to a Layer 5 full AI Operating System. It's both:

1. **A roadmap for the user** — what's possible to add and when it makes sense
2. **A coaching prompt for Claude** — when running `/weekly-wrap-up` or `/grow`, reference this to suggest the user's next CoS upgrade based on their current state

Update the checkboxes as the user adds capabilities (✅ done, 📋 pending, 🚫 not applicable).

---

## The 5-Layer Growth Path

```
┌─────────────────────────────────────────────┐
│  L5: ENGINE — Your entire company on AI     │
├─────────────────────────────────────────────┤
│  L4: SYSTEMIC — Company data flows into CoS │
├─────────────────────────────────────────────┤
│  L3: TEAM — Multi-seat with shared context  │
├─────────────────────────────────────────────┤
│  L2: CONNECTED — Full wedge install +       │
│                   services                  │
├─────────────────────────────────────────────┤
│  L1: FOUNDATION — Personal CoS (you're here)│
└─────────────────────────────────────────────┘
```

---

## Layer 1 — Foundation (Personal CoS)

You're here. The starter package gets you Layer 1.

- 📋 `CLAUDE.md` identity populated (run setup conversation)
- 📋 `context/life-plan.md` populated (5/10-year vision)
- 📋 `context/annual-plan.md` populated (current year OKRs + KPI scoreboard)
- 📋 `context/rocks.md` populated (current quarter)
- 📋 `context/scorecard.md` populated (weekly metrics)
- 📋 Memory layer turned on (first 2-3 memories saved)
- 📋 At least one MCP server connected (Notion or Google Calendar)
- 📋 Core commands working: `/day`, `/weekly-plan`, `/weekly-wrap-up`

**When you're solid at Layer 1:** running `/day` daily, doing weekly plans + wrap-ups, your context files reflect your actual reality (not skeletal placeholders).

---

## Layer 2 — Connected (Full Wedge Install)

Add services + automation. The CoS becomes meaningfully more powerful.

- 📋 Add `/debrief` — process meeting transcripts into action items (Fireflies, Otter, Granola, or pasted text)
- 📋 Add Slack MCP — your CoS posts daily summaries to a private channel
- 📋 Add Google Calendar MCP (if not already) — full calendar integration
- 📋 Add Rize MCP — productivity tracking integrated into `/day`
- 📋 Add Apollo MCP — lead enrichment for outreach
- 📋 Add `/prep` command — meeting prep on demand
- 📋 Add `/task` command — quick Notion task creation
- 📋 Add `/dashboard` command — visual snapshot of your CoS
- 📋 Build 1-2 custom commands specific to YOUR work

**Time to Layer 2 (DIY):** 2-4 weeks of incremental additions, or roughly 2 weeks with a guided install.

---

## Layer 3 — Team (Shared Intelligence Layer)

Each team member has their own CoS, with shared team context.

- 📋 Define team-shared context (rocks, scorecard, people DB visible across team)
- 📋 Set up team CoS instances (one per teammate)
- 📋 Build cross-CoS commands (`/team-pulse`, `/cascade-check`)
- 📋 Establish team rituals (shared weekly plan, scorecard sync)
- 📋 Role-based context (CEO's CoS thinks like a CEO; COO's like a COO)

**Time:** 2-6 weeks rollout depending on team size.

---

## Layer 4 — Systemic (Company Data + AI Client Brain)

Connect company systems. CoS becomes a company OS.

- 📋 CRM integration (HubSpot, Salesforce, Pipedrive)
- 📋 Finance data (QuickBooks, Stripe, banking)
- 📋 Support tickets / ops data
- 📋 Custom data sources via n8n, Make, or direct API
- 📋 AI Client Brain — client-facing CoS extension
- 📋 Workflow automation across systems

**Time:** Ongoing — each integration is 2-6 weeks.

---

## Layer 5 — Engine (Your Entire Company Running on AI)

Your CoS stops being a system of intelligence and becomes a system of action.

- 📋 AI agents that act on your data (not just answer questions about it)
- 📋 Multi-system automation across departments (sales, ops, finance, support)
- 📋 Customer/client-facing AI workflows
- 📋 Continuous learning across the entire company
- 📋 Every Layer 1-4 capability integrated and feeding each other

This is the "everything connects to everything" stage. Most companies take 6+ months to reach meaningful depth at Layer 5.

---

## How to Add Anything

You don't need to figure out the tech. Just ask Claude:

> *"Help me add [item] to my CoS."*

Claude walks you through: the connection (`.mcp.json`), the configuration, the usage opinions doc (`context/integrations/[tool].md`), the new commands. **The pattern is consistent across every addition.**

---

## Need Help?

Three paths:

- 🆓 **Free 7-Day Email Course** — Deeper guide to using your CoS at Layer 1 + starting Layer 2. [Sign up](https://cos.hyperedge.studio/course)
- 🤔 **Stuck on a specific addition?** [Book a 30-min Unstuck call with Brandon](https://cos.hyperedge.studio/book)
- 🛠️ **Want a layer built for you?** Hyperedge installs Layers 2-5. [Talk to Hyperedge](https://hyperedge.studio)

---

## How to Use This for Suggestions (Claude logic)

When the user runs `/grow` or you're surfacing a suggestion at the end of `/weekly-wrap-up`:

1. Check what they have today — which files are populated, which MCPs are connected, which commands are defined
2. Find the lowest-numbered Layer with unchecked items
3. Within that layer, pick the item with the highest impact for THEIR specific role (referenced from `CLAUDE.md`)
4. Surface it: *"Based on what you did this week, the next thing I'd add to your CoS is **[item]**. Here's why: [1-2 sentences]. Want me to walk you through it?"*

Update the checkboxes (📋 → ✅) when capabilities ship.
