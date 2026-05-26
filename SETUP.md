# Setup Guide

The full install runbook for your AI Chief of Staff. If you just want the quick start, see [README.md](README.md). This file goes deeper.

---

## Before You Start

You'll need:
- A computer (Mac or Windows)
- A Claude account ([sign up free](https://claude.ai))
- Under 30 minutes for first install (most of which is just answering Claude's questions, not technical setup)

You do NOT need:
- Coding experience
- Comfort with the terminal (optional but helpful)
- Any specific tools beyond Claude Code

---

## Step 1: Install Claude Code Desktop

1. Go to [docs.claude.com/claude-code](https://docs.claude.com/claude-code)
2. Download the desktop app for your operating system (Mac or Windows)
3. Install it like any other app
4. Sign in with your Claude account

**Why Desktop and not the web app?** The desktop app can read files on your computer. Your CoS lives as files, so it needs the desktop app.

---

## Step 2: Open Claude Code in an Empty Folder, Paste a Prompt

The simplest path — no GitHub account, no git, no ZIP. Claude downloads the starter for you on the first message.

1. Make an empty folder somewhere on your computer (e.g., `Documents/my-ai-cos`).
2. Open Claude Code Desktop → **File → Open Folder** → pick that folder.
3. Paste this prompt into the chat:

```
Hi! I want to set up an AI Chief of Staff in this folder.
Download the starter kit from
https://github.com/brandonpassley/ai-chief-of-staff-starter
into this folder (curl + tar, no git needed). Then read the
framework files and walk me through setup. Lead the
conversation. Push back on thin answers. Write to the files
as we go.
```

Claude will download the starter, read the framework files, and start the walkthrough. **You don't type into the markdown files.** Claude does. You have a conversation.

> 💡 **Skip the typing for the basics:** When Claude starts on `CLAUDE.md`, you can paste your LinkedIn URL/text, drop a screenshot of your profile or personal site, or paste any existing bio. Claude will pre-fill Name, Role, and Background — then you only have to answer the parts only you can (priorities, working style, how you want to be coached).

Most operators take 3-5 setup conversations spread across their first week:
- **Day 1:** CLAUDE.md (~15 min)
- **Day 2-3:** life-plan.md, annual-plan.md, rocks.md (~30 min each)
- **Day 4-5:** scorecard.md, people.md (~15 min each)
- **Week 2:** Run `/day` daily; add MCP servers as needed

---

### Alternative install paths

Skip this section unless you want to grab the files yourself (e.g., you want git version history so you can roll back changes Claude makes).

**GitHub Template:** [Go to the repo](https://github.com/brandonpassley/ai-chief-of-staff-starter) → click **"Use this template"** → create your own private copy → open in Claude Code Desktop.

**Git clone:**
```bash
git clone https://github.com/brandonpassley/ai-chief-of-staff-starter.git my-ai-cos
cd my-ai-cos
```
Then open the `my-ai-cos` folder in Claude Code Desktop.

**ZIP download:** On the repo, click **Code → Download ZIP** → extract → open the folder in Claude Code.

⚠️ **Mac note:** The starter includes hidden files (`.claude/`, `.gitignore`, `.mcp.json.example`). Finder hides files starting with a dot by default. Press **`Cmd + Shift + .`** to toggle them visible. The hidden files DO get downloaded and DO work — they're just invisible in Finder. If you ever copy/move the folder, make sure hidden files come along, or slash commands and MCP config won't work.

If you used one of these alternative paths, kick off setup with this prompt instead of the one above:

```
Hi! I'm setting up my AI Chief of Staff. Read the framework
files in this project — they're set up but mostly empty. Then
greet me and walk me through filling in the first one. Lead the
conversation. Push back on thin answers. Write to the files as
you learn what I tell you. Start now.
```

---

## Step 3: Run Your First Slash Command

Once `CLAUDE.md` is populated, type `/day` in the chat. Claude will:
- Read your CLAUDE.md
- Generate your first morning dashboard
- End with a Coach's Pulse

If you have Notion or Calendar connected (you don't yet — that's Step 4), it'll pull from those too. If not, it'll prompt you to add them.

Other commands available immediately:
- `/weekly-plan` — Sun/Mon plan (once rocks.md is populated)
- `/weekly-wrap-up` — Fri review
- `/dashboard` — generate your visual dashboard
- `/grow` — suggest your next CoS upgrade
- `/debrief` — process a call transcript

---

## Step 4: Connect Your First Tool (MCP Server)

Your CoS gets meaningfully more useful when it can read your real data. The most useful first additions:

| Tool | Why first | Difficulty |
|---|---|---|
| **Notion** | Tasks, people, projects — your operational data | Easy |
| **Google Calendar** | Meetings, time blocks | Easy |
| **Slack** | Daily post target, team comms | Medium |

To add any tool, just ask Claude:

```
Help me add Notion to my CoS.
```

Claude will walk you through:
1. Getting the API token / OAuth
2. Editing `.mcp.json`
3. Restarting Claude Code
4. Creating `context/integrations/notion.md` with YOUR usage opinions
5. Testing with a sample query

Apply the same pattern for any MCP server. The framework's `context/integrations/` folder is designed for this — one doc per tool.

---

## Git Basics (5-Minute Version for Non-Coders)

Git tracks every change to your CoS. You can roll back if Claude breaks something. You don't need to learn the full tool — just three commands.

### One-time setup

- **Mac:** Git is built-in. Skip to "The three commands."
- **Windows:** Install [Git for Windows](https://git-scm.com/download/win) (use the defaults).

### The three commands

1. **`git status`** — see what's changed since the last save point
2. **`git add .`** — stage all changes (mark them ready to save)
3. **`git commit -m "your message here"`** — save them with a description

### When to commit

- After any meaningful update to your CoS (new rock, new client file, new command)
- At the end of any work session you'd be sad to lose
- Whenever Claude does a big update for you

### The lazy way

Just tell Claude: *"commit my recent changes."* Claude will:
1. Check what's changed
2. Stage them
3. Commit with a descriptive message
4. Tell you what landed

That's enough git for 99% of CoS use cases.

### Optional: push to GitHub for backup

If your CoS lives in a GitHub repo (Path A or B above), you can push changes:

```bash
git push
```

Or ask Claude: *"push my changes to GitHub."*

---

## Common Issues

### "Slash commands aren't showing up"
- Make sure your project has a `.claude/commands/` folder (case-sensitive)
- Make sure command files end in `.md`
- Restart Claude Code after adding new commands

### "Claude can't find a file I just edited"
- The file may be in the wrong location. Ask Claude: *"where should [filename] live?"*
- Or run `git status` to see what changed.

### "I lost a file Claude wrote"
- If you committed before losing it: `git log` to find the commit, then ask Claude to help you restore.
- If you didn't commit: it's likely in your Claude Code "undo" history (Cmd/Ctrl+Z while focused on the file).

### "The Mac hidden files trick isn't working"
- `.claude/` (with dot prefix) should appear when you press `Cmd + Shift + .`
- If not, restart Finder (hold Option, right-click Finder icon in dock → Relaunch)

### "I want to start over"
- Delete your project folder
- Run Step 2 again (paste the prompt into a fresh empty folder, or re-clone)
- Your old CLAUDE.md content can be restored if you have it in git history

---

## What to Do Next

After initial install:

1. **Run `/day` every morning** for the first week. Watch the dashboard get better as your context files fill out.
2. **Run `/weekly-plan` and `/weekly-wrap-up`** at the start and end of each week.
3. **When you hit something missing** (an MCP server, a new command, a folder structure question), ask Claude.
4. **Run `/grow`** once a week. It'll tell you what to add next.

Most operators are at Layer 2 (full wedge install) within 2-4 weeks of starting Layer 1. The framework scales with you.

---

## Need Help?

- 🆓 **Free 7-Day Email Course** — Deeper guide to using your CoS. [Sign up](https://cos.hyperedge.studio/course?utm_source=setup&utm_medium=starter-kit&utm_campaign=ai-cos-starter&utm_content=course)
- 🤔 **Stuck on something specific?** [Book a 30-min Unstuck call with Brandon](https://cos.hyperedge.studio/book?utm_source=setup&utm_medium=starter-kit&utm_campaign=ai-cos-starter&utm_content=unstuck)
- 🛠️ **Want it built for you?** Hyperedge installs the full Layer 2 system. [Talk to Hyperedge](https://hyperedge.studio?utm_source=setup&utm_medium=starter-kit&utm_campaign=ai-cos-starter&utm_content=dfy)
- 💬 **Quick questions?** [Open an issue on GitHub](https://github.com/brandonpassley/ai-chief-of-staff-starter/issues)

---

Built by [Brandon Passley](https://hyperedge.studio?utm_source=setup&utm_medium=starter-kit&utm_campaign=ai-cos-starter&utm_content=byline) — founder of Hyperedge. MIT licensed.
