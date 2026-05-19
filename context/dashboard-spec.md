---
status: complete  # ships populated as the default spec
last_updated: 2026-05-19
---

# Dashboard Spec

## How Claude Uses This File

This is the **authoritative spec** for `dashboard.html`. When `/dashboard` runs, Claude reads this file (if it exists) and uses these standards instead of the defaults baked into `/dashboard.md`. Edit this file to customize the dashboard without touching the command.

If you want a section added, removed, or styled differently — edit this file. The next `/dashboard` run will reflect the changes.

---

## File: `dashboard.html`

- **Location:** project root
- **Format:** single-file HTML with inline CSS — no external dependencies
- **Behavior:** idempotent — overwritten on every `/dashboard` run

## Aesthetic Principles

- **Clean over flashy** — system font stack, generous whitespace, muted colors
- **Mobile responsive** — flexbox/grid; works at any width
- **Print-friendly** — sensible defaults when printed
- **Scannable in 10 seconds** — the most important info at the top
- **No fluff** — every section earns its space; cut anything that's filler

## Color Palette

| Use | Color | Hex |
|---|---|---|
| Background | Warm off-white | `#fafaf9` |
| Card / panel background | White | `#ffffff` |
| Primary text | Near-black | `#1a1a1a` |
| Secondary text | Muted gray | `#444` |
| Subtle / metadata | Light gray | `#888` |
| Border | Very light gray | `#e5e5e5` |
| Highlight (empty state) | Pale yellow | `#fef9c3` (background) / `#facc15` (accent) |
| Status: On Track | Green | `#16a34a` |
| Status: At Risk | Orange | `#ea580c` |
| Status: Off Track | Red | `#dc2626` |

## Default Sections (in order)

1. **Header** — User's name + role + current quarter/week + last updated timestamp
2. **Top 3 Priorities** — pulled from `CLAUDE.md`
3. **This Week** — MIT + Big 3 (from most recent `history/weekly-plan-*.md`)
4. **Current Quarter Rocks** — table: Rock | OKR | Status | Last updated
5. **Weekly Scorecard Snapshot** — current week's row + key targets
6. **Connected Tools** — from `.mcp.json` + integration docs in `context/integrations/`
7. **Active Commands** — grid of cards from `.claude/commands/`
8. **Recent Wins** — last 5-10 completed tasks (Notion) OR recent wrap-up highlights from `history/`
9. **CoS Growth** — table or progress bars from `context/expansion-roadmap.md`
10. **Suggested Next Step** — from `/grow` logic (one suggestion + 1-line why)
11. **Footer** — last updated timestamp + "Run `/dashboard` to refresh"

## Section Population Logic

For each section, if the underlying data source is **empty or not yet populated**, render a yellow "empty-state" callout pointing the user to the right next action. **Don't break the section — guide the user.**

Examples:
- Empty `CLAUDE.md` → *"Not yet populated — ask Claude to set up CLAUDE.md first."*
- No `.mcp.json` → *"No MCP servers connected yet. To add one, ask Claude: 'help me add [tool] to my CoS.'"*
- Empty `rocks.md` → *"Not yet populated — set up `context/rocks.md`. Ask Claude: 'let's set up my Q[N] Rocks.'"*

## Customization Patterns

### Add a new section
Tell Claude: *"add a section to the dashboard showing my [thing]."*

Claude will:
1. Update this `dashboard-spec.md` with the new section spec
2. Update `/dashboard.md` command if needed to fetch the data
3. Regenerate `dashboard.html` on the next `/dashboard` run

### Remove a section
Tell Claude: *"remove the [section name] section from my dashboard."*

### Change styling
Edit the CSS variables in this file. Common edits:
- Change font: edit `body { font-family: ... }` in the CSS spec
- Change accent color: edit the highlight + status colors
- Add/remove cards: edit the grid section

### Add custom data sources
If you want the dashboard to pull from a tool that's not in the default list (e.g., a custom API, Stripe MRR, etc.):
1. Add a section to `context/integrations/[tool].md` for that data source
2. Update this spec with the new section
3. Update `/dashboard.md` with the fetch logic

Claude will walk you through all three.

## What NOT to Put on the Dashboard

- Anything sensitive (passwords, tokens, API keys) — never inline in HTML
- Long lists (>15 items) — link to the source file instead
- Stale data without timestamps — always show "last updated"
- More than 11-12 sections total — beyond that, it's no longer scannable

## Review Cadence

Update this spec when:
- You want to change what the dashboard shows
- You realize a section is taking up space without giving value
- You add a new tool/integration whose data should be on the dashboard
- You want a different aesthetic
