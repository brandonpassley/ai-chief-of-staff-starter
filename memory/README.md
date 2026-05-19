# memory/

Your CoS's long-term memory. Persists across all conversations.

## Auto-managed

This folder is managed by Claude automatically. You don't create files here by hand.

When you say something like *"remember this for me"* or Claude notices a recurring pattern, it writes a memory file here. The `MEMORY.md` index tracks them all.

## The 4 Memory Types

| Type | What it holds |
|---|---|
| **user** | Facts about you (role, preferences, knowledge) |
| **feedback** | Corrections and rules (what to do / not do) |
| **project** | Current work context (active engagements, status) |
| **reference** | Where information lives (external systems, links) |

## Where memory actually lives

For Claude Code, memory entries are stored at:
`~/.claude/projects/{project-path}/memory/`

That path is in your user home directory, not this repo. It survives across machines if you sync `~/.claude/`. This README documents the system; the actual memories live there.
