# context/projects/

One file per **major project or engagement** that deserves its own tracker.

## When to add a project file

A project gets its own file when:
- It has **defined scope** (not just open-ended work)
- It has **a deadline or milestone date**
- There are enough moving pieces that referencing it in conversation needs a doc
- Multiple people / dependencies are involved

If you just have a task or a small one-off, that goes in your Notion task tracker. This folder is for **substantial engagements** (typically $5K+ value or 4+ weeks of work).

## File naming

`[project-name].md` — kebab-case, no spaces.

Examples:
- `client-portal-rebuild.md`
- `q3-website-redesign.md`
- `pricing-revamp.md`

## What goes in a project file

See `_example-project.md` for the full structure. Quick version:
- Scope + deliverables
- Owner + key collaborators
- Status + milestones
- Current week's focus
- Open decisions
- Risks / blockers
- Decision log
- Weekly tracker

## Adding a new project

Just tell Claude:

> *"Add a project tracker for [project name]."*

Claude will ask 5-7 setup questions and create the file using the template.

## Relationship to clients/

If a project is for a specific client, that's fine — the client file (in `context/clients/`) tracks the *relationship*, and the project file here tracks the *specific engagement*. They cross-reference each other.
