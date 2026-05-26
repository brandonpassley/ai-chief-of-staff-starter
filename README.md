# Your AI Chief of Staff — Starter Kit

A free, opinionated starter framework for building your own AI Chief of Staff using Claude Code.

> "I built one for myself in 2025. Now it runs every morning, plans every week, and remembers what matters. Here's how to build yours."
> — [Brandon Passley](https://hyperedge.studio)

---

## What This Is

A working starter repo for an AI Chief of Staff. Drop the folder on your computer, install Claude Code, and start a conversation. Claude reads the framework files in this project and walks you through setting up your CoS — your identity, your life plan, your annual OKRs, your quarterly Rocks, your weekly scorecard.

**You don't fill in forms. You have conversations.**

---

## The 4-Layer Framework

| Layer | What | Files |
|---|---|---|
| **Identity** | Who you are. How you work. | `CLAUDE.md` |
| **Strategy** | What matters. What you're building. | `context/life-plan.md`, `annual-plan.md`, `rocks.md`, business V/TOs |
| **Operations** | How you run day-to-day. | `context/scorecard.md`, `people.md`, `.claude/commands/*` |
| **Reflection** | How you improve. | `memory/`, `history/` |

---

## Quick Start

No GitHub account, no git, no ZIP downloads. Just:

1. **Install [Claude Code Desktop](https://docs.claude.com/claude-code)** (macOS or Windows)
2. **Make an empty folder** anywhere on your computer (e.g., `Documents/my-ai-cos`)
3. **Open that folder in Claude Code** (File → Open Folder)
4. **Paste this prompt:**

```
Hi! I want to set up an AI Chief of Staff in this folder.
Download the starter kit from
https://github.com/brandonpassley/ai-chief-of-staff-starter
into this folder (curl + tar, no git needed). Then read the
framework files and walk me through setup. Lead the
conversation. Push back on thin answers. Write to the files
as we go.
```

5. **Have a conversation.** Claude leads.

That's it. You'll have a working **Layer 1 AI Chief of Staff** in under 30 minutes — and most of that is just answering Claude's questions, not technical setup. Prefer to clone the repo yourself? See [SETUP.md](SETUP.md) for alternative install paths.

---

## What's Inside

```
.
├── CLAUDE.md                          ← Identity layer (always loaded)
├── context/
│   ├── life-plan.md                   ← 5/10-year vision + wealth code
│   ├── annual-plan.md                 ← Yearly OKRs + KPI scoreboard
│   ├── rocks.md                       ← Quarterly EOS Rocks
│   ├── scorecard.md                   ← Weekly metrics tracker
│   ├── people.md                      ← Relationship intelligence
│   ├── expansion-roadmap.md           ← What to add as you grow
│   ├── dashboard-spec.md              ← Visual dashboard standards
│   ├── clients/                       ← One file per client (when you have several)
│   ├── projects/                      ← One file per major engagement
│   └── integrations/                  ← Tool-specific usage opinions
├── .claude/
│   └── commands/                      ← Slash commands (rituals)
│       ├── day.md
│       ├── weekly-plan.md
│       ├── weekly-wrap-up.md
│       ├── debrief.md
│       ├── dashboard.md
│       └── grow.md
├── memory/                            ← Auto-managed by Claude (don't touch)
├── history/                           ← Weekly plan + wrap-up archive
├── dashboard.html                     ← Your visual CoS dashboard
└── SETUP.md                           ← Full install guide
```

---

## The Growth Path

| Layer | What it adds | DIY time |
|---|---|---|
| **L1 — Foundation** (free) | Personal CoS, just for you | 30 min |
| **L2 — Connected** | All your services connected (Notion, Slack, Calendar, etc.) | 1-2 wks |
| **L3 — Team** | Multi-seat CoS with shared team context | 2-4 wks |
| **L4 — Systemic** | Company data integrations + AI Client Brain | Ongoing |
| **L5 — Engine** | Your entire company running on AI | Ongoing |

See [`context/expansion-roadmap.md`](context/expansion-roadmap.md) for the full breakdown.

---

## Why This Is Different

This isn't a fill-in-the-blank template. Every file in this repo is built as **instructions for Claude** — what to ask, what good looks like, when to push back on weak answers. You drop in the folder, then talk to Claude the way you'd onboard a real chief of staff. Claude writes the files.

Most people have 3-5 setup conversations spread across their first week. None involve opening a markdown file.

---

## Need Help?

Three paths:

- 🆓 **Free 7-Day Email Course** — How to actually use your AI CoS (life plan, OKRs, Rocks, scorecard, advanced commands). [Sign up](https://cos.hyperedge.studio/course)
- 🤔 **Stuck on something specific?** [Book a 30-min Unstuck call with Brandon](https://cos.hyperedge.studio/book)
- 🛠️ **Want it built for you?** Hyperedge installs the full Layer 2 system. [Talk to Hyperedge](https://hyperedge.studio)

---

## About

Built and maintained by [Brandon Passley](https://hyperedge.studio), founder of Hyperedge (AI operating systems for founder-led B2B agencies). Brandon runs two businesses and lives this framework every day.

## License

MIT — use it however you want. Star the repo if it's useful.
