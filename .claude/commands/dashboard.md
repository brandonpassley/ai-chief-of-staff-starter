---
description: Build or update your visual AI Chief of Staff dashboard (idempotent)
---

# /dashboard — Visual CoS Dashboard

Generates or updates `dashboard.html` — a single-file visual snapshot of your AI Chief of Staff state.

## How Claude Uses This Command

The user types `/dashboard`. Build the dashboard from current CoS state, or update it if `dashboard.html` already exists.

This command is **idempotent**: creates the file if missing, updates it if present. Always overwrites with the latest snapshot.

---

## Step 1 — Gather Current State (parallel reads)

Read in parallel:
- `CLAUDE.md` — name, top 3 priorities, domains
- `context/rocks.md` — current quarterly Rocks + statuses
- `context/scorecard.md` — this week's row, monthly summary, Rock progress tracker
- `context/expansion-roadmap.md` — which capabilities are ✅ vs 📋
- Most recent `history/weekly-plan-*.md` — this week's MIT + Big 3
- `.mcp.json` (if exists) — connected MCP servers
- `.claude/commands/` listing — defined slash commands
- `memory/MEMORY.md` (if accessible) — count of memory entries by type

If `context/dashboard-spec.md` exists, use it as the authoritative spec for styling and content. Otherwise, use the default spec embedded below.

---

## Step 2 — Build the HTML

Generate a single-file `dashboard.html` at the project root. **Standards:**

- **Single file** — no external CSS, JS, or images. Inline everything.
- **No dependencies** — no CDNs, no frameworks. Pure HTML + CSS.
- **Mobile responsive** — uses flexbox/grid, works at any width
- **Clean aesthetic** — system font stack, generous whitespace, muted colors
- **Print-friendly** — sensible defaults if the user prints it

### Default Sections (in order)

1. **Header** — User's name + role + current quarter/week (e.g., *"Brandon Passley — Q2 W7 — May 19, 2026"*)
2. **Top 3 Priorities** — pulled from `CLAUDE.md`
3. **This Week** — MIT + Big 3 (from latest `history/weekly-plan-*.md`)
4. **Current Quarter Rocks** — table with Rock | OKR | Status | Last updated
5. **Weekly Scorecard Snapshot** — current week's row + key targets
6. **Connected Tools** — list of MCP servers with status (from `.mcp.json` + heuristic check)
7. **Active Commands** — list of slash commands from `.claude/commands/`
8. **Recent Wins** — last 5-10 completed tasks (if Notion connected) or recent wrap-up highlights
9. **CoS Growth** — visual checklist of expansion roadmap items (✅ done, 📋 pending)
10. **Suggested Next Step** — pulled from `/grow` logic (one suggestion + 1-line why)
11. **Footer** — *Last updated: [datetime]* + *Run `/dashboard` to refresh*

### Default Styling

```css
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", system-ui, sans-serif;
  max-width: 1200px; margin: 0 auto; padding: 32px 24px;
  background: #fafaf9; color: #1a1a1a; line-height: 1.5;
}
h1 { font-size: 28px; margin-bottom: 4px; }
h2 { font-size: 18px; margin-top: 32px; margin-bottom: 12px; color: #444; }
table { width: 100%; border-collapse: collapse; margin: 8px 0; }
th, td { padding: 8px 12px; text-align: left; border-bottom: 1px solid #e5e5e5; }
th { background: #f5f5f4; font-weight: 600; }
.status-on-track { color: #16a34a; }
.status-at-risk { color: #ea580c; }
.status-off-track { color: #dc2626; }
.subtle { color: #888; font-size: 14px; }
section { margin-bottom: 24px; }
.grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 16px; }
```

---

## Step 3 — Write the File

Save to `dashboard.html` at the project root (overwrites if exists).

---

## Step 4 — Confirm

After writing, tell the user:

> *Dashboard updated → `dashboard.html`. Open it in your browser to view. Run `/dashboard` anytime to refresh.*

If the user wants to customize:
- Tell them about `context/dashboard-spec.md` (or create it if it doesn't exist)
- Or they can just say *"update the dashboard to also show X"* and Claude updates both `/dashboard.md` and `context/dashboard-spec.md`

---

## Customization Pattern

To customize what the dashboard shows or how it looks:
- Edit `context/dashboard-spec.md` (create it if needed) — that becomes the authoritative spec
- Or have a conversation: *"add a section to the dashboard showing my Notion task completion rate this month"*

The command file (`/dashboard`) reads `context/dashboard-spec.md` if it exists and uses those standards instead of the defaults above.

---

## Rules

- Always idempotent — same data → same output
- Never break existing dashboard sections without explicit instruction
- Pull data from source files, don't hard-code values
- Date format: *"May 19, 2026"* or *"2026-05-19"* — never ambiguous *"5/19"* alone
- Status badges: ✅ ⚠️ ❌ for Rocks (use matching CSS classes)
- If a data source is empty (e.g., `rocks.md` is empty), show the section with a *"Not yet populated — ask Claude to set this up"* note instead of breaking
- Output should look at home on Brandon's laptop AND on a phone
