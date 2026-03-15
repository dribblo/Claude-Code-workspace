# Claude Code Workspace

> A simple way to make Claude Code remember who you are.

I got tired of re-explaining myself every time I opened Claude Code. So I built a workspace structure that makes it context-aware from the first message. Clone it, run through a short setup, and every future session starts already knowing you.

**Requires [Claude Code](https://docs.anthropic.com/en/docs/claude-code)** — available in the terminal or inside the Claude desktop app.

<!-- TODO: Add demo GIF showing the wizard and mode selector in action -->
<!-- ![Claude Code Workspace demo](demo.gif) -->

---

## How it works

Claude Code automatically reads a file called `CLAUDE.md` when it starts. This is a built-in feature — not something this project adds.

What this project does is give you a ready-made `CLAUDE.md` and a set of files that work together to make Claude context-aware. Everything here is prompt engineering — there's no plugin, no extension, no code. Just structured markdown files that tell Claude how to behave.

```
Your workspace/
  CLAUDE.md          ← auto-read by Claude Code at session start
  .claude/
    modes/
      work.md        ← context for work tasks
      my-project.md  ← context for a specific project
      learning.md    ← context for study sessions
    templates/       ← output formats you use repeatedly
    skills/          ← reusable shortcuts
    config.json      ← your name, default mode, preferences
```

Every session starts like this:

```
Claude: Hey Daniel. What's this about?
  1. work  (default)
  2. my-project
  3. learning

You: 1

Claude: Work mode. What's the task?
```

That's it. No re-explaining. No setup. Just work. You can switch modes mid-session anytime.

---

## Quickstart

Open Claude Code and paste this:

```
git clone https://github.com/dribblo/Claude-Code-Workspace.git && cd Claude-Code-Workspace
```

Then just say **"let's go"**.

Claude reads `CLAUDE.md`, sees it's your first time, and walks you through a setup wizard — about 10 minutes of questions about your work, your style, and what you need help with.

After that, every time you open Claude Code in this folder, it picks up where you left off.

---

## Modes

A mode is a markdown file that tells Claude:

- **Who you are** in this context
- **What this mode is for**
- **How you want Claude to behave**
- **Background knowledge** it should always have
- **A kick-off question** to open every session

The wizard builds these based on your answers. Here are some examples of what people create:

| Mode | Use case |
|---|---|
| `work.md` | Day-to-day tasks, documents, communication |
| `email.md` | Fast email drafts in your voice |
| `strategy.md` | Research, analysis, one-pagers |
| `learning.md` | Studying, understanding new topics |
| `personal.md` | Life admin, planning, personal projects |

---

## Things you can say

These aren't built-in Claude Code commands — they work because `CLAUDE.md` instructs Claude to respond to them. They're reliable in most sessions, but they're prompt engineering, not native features.

| Phrase | What it does |
|---|---|
| `switch mode` | Change to a different mode mid-session |
| `status` | See your current mode and recent session history |
| `reset` | Re-run the wizard from scratch (backs up your files first) |
| `update` | Pull the latest improvements from the template repo |
| `export` | Create a shareable, anonymised version of your setup |

---

## What happens behind the scenes

All of this works through `CLAUDE.md` — a file Claude Code reads automatically. Here's the gist of what it does:

```
1. Reads your config (name, default mode)
2. Loads all your context files (people, glossary, rules, style, memory)
3. Shows your modes and asks "What's this about?"
4. Loads the chosen mode and asks the kick-off question
```

It also instructs Claude to:

- **Save changes automatically** — when you update your workspace files, Claude commits them so nothing gets lost
- **Write a session summary** — at the end of each session, Claude appends a short summary to your memory file
- **Suggest additions** — if Claude notices new terms, people, or decisions during a session, it offers to add them to your workspace

These are instructions, not guarantees. They work well in practice, but they depend on Claude following the prompt — which it usually does, but not always. You can see the full `CLAUDE.md` in the repo.

---

## Why I built this

Claude Code is powerful out of the box — but blank. Every session starts the same way: you explain who you are, what you're working on, how you like to communicate. Again. And again.

This is my solution — a file structure that Claude Code reads automatically. No plugin, no extension, no installs. It works today with the Claude Code you already have. I'm sharing it because it's been useful to me and might be useful to you.

---

## Contributing

Contributions welcome — especially new mode templates. See `CONTRIBUTING.md`.

---

## License

MIT — use it, fork it, build on it.
