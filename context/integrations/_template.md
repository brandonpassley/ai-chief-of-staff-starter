---
status: empty  # empty | partial | complete
tool: {{TOOL NAME}}
last_updated:
---

# {{TOOL NAME}} Integration

## How Claude Uses This File

This file holds **YOUR specific usage opinions** for {{TOOL NAME}}. When Claude uses the {{TOOL NAME}} MCP, it reads this file to know:
- Which {{databases / channels / pipelines / etc.}} matter
- How you organize things in {{TOOL NAME}}
- What voice / tone to use when posting / writing
- What's in-scope vs out-of-scope for AI to touch

When this file is empty, Claude should walk through setup questions before using the {{TOOL NAME}} MCP for anything substantive.

## Coaching Standards

A strong integration doc has:
- **A clear scope** — what Claude can read / write / modify vs. what's read-only
- **Naming conventions** — your project / channel / pipeline names so Claude doesn't have to guess
- **Voice opinions** — if Claude posts on your behalf, how should it sound?
- **Guardrails** — anything Claude should NEVER do in this tool (e.g., never delete records, never DM external contacts)

---

## Connection

- **MCP server:** {{e.g., @vendor/tool-mcp-server}}
- **Auth method:** {{OAuth / API key / Bearer token}}
- **Connected:** {{Date}}

## Scope

### Claude CAN:
- {{e.g., "Read all pages in the Tasks database"}}
- {{e.g., "Create new tasks with priority and project tags"}}
- {{e.g., "Update task status (Not started → In progress → Done)"}}

### Claude CANNOT (or should ask first):
- {{e.g., "Delete records"}}
- {{e.g., "Send external messages"}}
- {{e.g., "Modify shared team data without explicit instruction"}}

## Your {{TOOL NAME}} Structure

[This section is the meat — describe how YOU specifically organize this tool. Be concrete.]

{{Examples by tool type:}}

**If a database tool (Notion, Airtable):**
- Database / table names + IDs
- What each one is for
- Key fields Claude should know about

**If a messaging tool (Slack, Discord):**
- Channel names + their purposes
- Voice / tone for posts
- When Claude should auto-post vs ask first

**If a CRM (HubSpot, Salesforce):**
- Pipeline stages
- Deal fields that matter
- ICP filters
- Lifecycle stages

**If a calendar:**
- Which calendars for what
- Time block conventions
- Color meanings if you use them

## Voice / Tone (when Claude writes via this tool)

- {{e.g., "Posts in #chief-of-stuff use plain bullets, no fluff, emoji headers"}}
- {{e.g., "Slack messages to external clients use full sentences and a more formal register"}}
- {{e.g., "Email follow-ups are short — 3 sentences max, action-oriented"}}

## Coaching Prompts (for Claude)

When using {{TOOL NAME}}:
- {{e.g., "Always verify the database before writing — there are multiple similar-named DBs"}}
- {{e.g., "When creating a new task, infer Project from context if obvious; ask if not"}}
- {{e.g., "Before bulk operations (>5 records), confirm with user"}}

---

## Review Cadence

Update this file when:
- You restructure your {{TOOL NAME}} setup
- You change naming conventions
- You realize Claude is doing something wrong consistently (add a guardrail)
- You add a new use case Claude should know about

To update: tell Claude *"let's update my {{TOOL NAME}} integration doc."*
