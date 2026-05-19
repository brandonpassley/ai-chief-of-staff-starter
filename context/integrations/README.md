# context/integrations/

Tool-specific usage opinions live here. One file per connected MCP server (tool).

## Why this folder exists

When you connect a new tool to your CoS (Notion, Slack, HubSpot, etc.), the technical connection lives in `.mcp.json`. But the *opinions about how YOU specifically use that tool* — which databases matter, which channels for what, your pipeline stage names, voice/tone for posts — those need their own home. This is it.

## File naming

One file per tool, named after the tool: `notion.md`, `slack.md`, `calendar.md`, `hubspot.md`, etc.

## How to add a new integration

You don't need to read any technical docs. Just tell Claude:

> *"Help me add [tool] to my CoS."*

Claude will:
1. Walk you through OAuth + `.mcp.json` setup
2. Create the integration doc here using `_template.md` as the structure
3. Ask you 3-5 quick questions about how you use the tool
4. Update `CLAUDE.md` Connected Tools table

## What's in this folder

- **`_template.md`** — the structure every integration doc follows
- **`notion.md`** — example (Notion is the baseline MCP for most CoS setups)
- *(Add new files as you connect new tools)*
