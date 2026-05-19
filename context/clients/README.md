# context/clients/

One file per client (or major customer). Use when you have **multiple clients** worth tracking individually.

## When to add a client file

A client gets its own file when:
- They're an **active engagement** (current or recent)
- There's enough context that "tell Claude everything about this client" needs a doc
- Status, scope, history, or open loops would be useful to reference repeatedly

If you have **1-2 clients**, you might just keep notes in `context/business.md`. Folder pays off around 3+ clients.

## File naming

`[client-name].md` — kebab-case, no spaces.

Examples:
- `acme-corp.md`
- `widgetco.md`
- `craft-haus.md`

## What goes in a client file

See `_example-client.md` for the full structure. Quick version:
- Status (active, dormant, churned)
- ICP / their role / industry
- Engagement scope + pricing
- Key contacts
- Engagement history / timeline
- Current open loops
- Decision log

## Adding a new client

Just tell Claude:

> *"Add [client name] to my clients folder."*

Claude will ask 5-7 setup questions and create the file using the template.
