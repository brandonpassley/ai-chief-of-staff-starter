---
status: empty  # empty | partial | complete
tool: Notion
last_updated:
---

# Notion Integration

## How Claude Uses This File

This file holds **YOUR specific Notion setup** — which databases matter, what fields are in them, how you organize things. When Claude uses the Notion MCP for tasks, people, or any data operation, it reads this file first.

When this file is empty, Claude should walk through setup before doing substantive Notion work. Ask:
- What databases do you have? (Tasks, People, Companies, Projects, etc.)
- Which one is your task tracker?
- What fields matter in your task DB? (Priority? Project? Due date? Assignee?)
- What are your priority labels? (e.g., "🔥 Today / ⏰ This Week / 📋 Backlog")
- What are your project tags?

---

## Connection

- **MCP server:** `@notionhq/notion-mcp-server`
- **Auth method:** Notion integration token
- **Connected:** {{Date}}

## Scope

### Claude CAN:
- Read pages and database entries
- Create new database entries (tasks, people, companies, etc.)
- Update existing entries (status, priority, fields)
- Search Notion content
- Build comments and follow-ups

### Claude SHOULD ASK FIRST:
- Before deleting any record
- Before bulk operations on >5 records
- Before modifying shared team data
- Before changing schema (adding/removing properties)

---

## Your Notion Databases

[Populate this section through conversation. Example structure below.]

### Example: Tasks Database
- **Database name:** Tasks Tracker
- **Database ID:** {{auto-fill after Claude queries Notion}}
- **Purpose:** All actionable to-dos across business + personal
- **Key fields:**
  - `Task name` (title)
  - `Status` (status: Not started / In progress / Done)
  - `Priority` (select: 🔥 Today / ⏰ This Week / 📋 Backlog / 🧊 Icebox)
  - `Project` (select: ⚡ Business / 💬 Social / 📺 YouTube / 🏄 Personal)
  - `Due date` (date)
  - `Description` (rich_text)
  - `Completed at` (date — set when status → Done)

### Example: People Database
- **Database name:** People
- **Purpose:** Warm contacts + relationship intelligence
- **Key fields:**
  - `Person` (title — full name)
  - `Title / Role` (rich_text)
  - `LinkedIn` (url)
  - `Email` (email)
  - `🏢 Company` (relation → Companies DB)
  - `Status` (select: Dormant / Cold / Warming / Friendly / Trusted / Client)
  - `Source` (select)
  - `Last touch` (date)
  - `Next touch` (date)
  - `Notes` (rich_text)

### Example: Companies Database
- **Database name:** Companies
- **Purpose:** Companies linked to people, for warm-list management
- **Key fields:**
  - `Company` (title)
  - `Website` (url)
  - `LinkedIn` (url)
  - `Notes` (rich_text)
  - `People` (relation → People DB)

---

## Defaults Claude Should Use

When creating a task without explicit instructions:
- **Status:** Not started
- **Priority:** ⏰ This Week (unless user says "today" or "urgent" → 🔥 Today)
- **Project:** Inferred from context (or ask if ambiguous)
- **Due date:** Leave blank unless user mentions a date

When creating a person entry:
- **Status:** leave empty (user judgment field)
- Apollo-enriched if user has Apollo MCP connected; otherwise from user info

When updating an existing entry: never overwrite a non-empty field unless explicitly told.

---

## Voice / Tone for Notion Content

- **Task names:** action verb + specific object ("Email Acme about pricing" not "Acme follow-up")
- **Task descriptions:** brief, future-self-as-reader ("On Tuesday's call we agreed to X — send Y by Friday")
- **People notes:** concrete + dated ("2026-05-19: had call with Eric — interested in 2-way referral; next step Brandon to send 1-pager")

---

## Coaching Prompts (for Claude)

- Always verify database before writing — multiple databases may have similar names
- When user says "create a task" without project: infer from context; ask if unclear
- Before bulk creates (>5 records), confirm scope
- Use mcp__notion__ tools, never use curl or other HTTP libraries to call Notion API
- Page IDs: when you create or look up a page, save the ID to memory for future reference

---

## Review Cadence

Update this file when:
- You add or rename a database
- You change field names or priority labels
- You realize Claude is consistently misclassifying something (add a default rule)
- You add new project tags

To update: tell Claude *"let's update my Notion integration doc."*
