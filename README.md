# claude-context

> The standard for Claude Code workspaces.

`claude-context` is an open convention for making Claude Code context-aware from the first message of every session. Instead of re-explaining who you are and what you're working on every time, Claude Code reads your workspace and asks which mode to start in.

---

## How it works

Claude Code automatically reads `CLAUDE.md` at the start of every session. `claude-context` defines what that file should contain — and how to structure the rest of your workspace — so Claude always starts informed, focused, and in the right mode.

```
Your repo/
  CLAUDE.md          ← auto-loaded by Claude Code. This is the plugin.
  .claude/
    branches/
      work.md        ← context for work tasks
      my-project.md  ← context for a specific project
      learning.md    ← context for study sessions
    config.json      ← your name, default branch, preferences
```

Every session starts like this:

```
Claude: Which branch today?
  1. work
  2. my-project
  3. learning

You: 1

Claude: Work mode. What's the task?
```

That's it. No re-explaining. No setup. Just work.

---

## Quickstart

### Option A — Use the wizard (recommended)

Copy the wizard prompt from `wizard.md` and paste it into a new Claude Code session. Claude will set up your entire workspace in a single conversation — creating the repo structure, interviewing you about your workflow, and generating personalised branch files.

### Option B — Manual setup

1. Copy `CLAUDE.md` into the root of your project
2. Create `.claude/branches/`
3. Copy a branch template from `branches/` and fill it in
4. Create `.claude/config.json` with your name and default branch
5. Open Claude Code — it reads `CLAUDE.md` automatically

---

## Branch files

A branch is a Markdown file that tells Claude:

- **Who you are** in this context
- **What this mode is for**
- **How you want Claude to behave**
- **Background knowledge** it should always have
- **A kick-off question** to open every session

| Branch | Use case |
|---|---|
| `work.md` | Emails, documents, meetings, professional communication |
| `personal.md` | Life admin, decisions, planning, personal projects |
| `learning.md` | Understanding topics deeply, studying, research |
| `creative.md` | Writing, brainstorming, ideation, creative projects |
| `project-template.md` | Blank template for any specific project |

---

## Why this exists

Claude Code is powerful out of the box — but blank. Every session starts the same way: you explain who you are, what you're working on, how you like to communicate. Again. And again.

`claude-context` solves this with a simple convention: a structured workspace that Claude Code understands from the first word. It's not a plugin, an extension, or a wrapper. It's a file structure and a spec. It works today, with the Claude Code you already have, with no installs.

---

## Contributing

Contributions welcome — especially new branch templates. See `CONTRIBUTING.md`.

---

## License

MIT — use it, fork it, build on it.
