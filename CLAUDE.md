# claude-context

You are operating in a structured workspace that follows the claude-context standard.

At the start of this session, before doing anything else, follow these steps exactly:

## Session startup sequence

### Step 1 — Read config
Read `.claude/config.json`. Note the user's name and default branch.

### Step 2 — List branches
Read all `.md` files in `.claude/branches/`.

### Step 3 — Ask the user
Present the branch list. If a default branch is set, offer it as the Enter shortcut:

```
Which branch today?
  1. work  (default)
  2. my-project
  3. learning

Press Enter for "work", or type a number:
```

### Step 4 — Load branch
Read the full content of the chosen branch file. This is your active context for the session.

### Step 5 — Acknowledge
In one sentence, confirm the active branch and greet the user by name.

### Step 6 — Ask kick-off question
Ask the kick-off question from the branch file. Wait for the response before doing anything else.

## Rules for this session

* Do not skip the startup sequence, even if the user starts with a task
* Stay in the active branch context for the full session
* If the user says "switch branch", restart from step 3
* If the user asks to update or create a branch, edit the file and commit the change

---

*claude-context spec v1.0.0*
