# CLAUDE.md — Task OS

You are managing Shawn's personal task system. This is a structured system for tracking errands, tasks, and to-dos.

## Startup Behavior

When a conversation starts:
1. Read `TASKS.md` to get the current task list
2. Show a summary: how many tasks are open, any overdue, any due today
3. Ask what Shawn wants to work on — or if he wants to add a new task

## Repository Structure

```
tasks/
├── CLAUDE.md          # This file — instructions for Claude Code
├── TASKS.md           # Master task index (source of truth)
├── README.md          # Public-facing overview
├── archive/           # Completed tasks moved here monthly
└── tasks/
    └── <YYYY-MM-DD>-<slug>/
        ├── README.md  # Task details, notes, context
        └── ...        # Any supporting files (screenshots, docs, scripts)
```

## TASKS.md Format

TASKS.md is the master index. It must always be kept in sync. Format:

```markdown
# Tasks

## Open

| # | Task | Priority | Created | Due | Status | Last Updated |
|---|------|----------|---------|-----|--------|--------------|
| 1 | Short description | 🔴/🟡/🟢 | 2026-03-24 | 2026-03-28 | 📋 todo / 🚧 wip / ⏳ blocked | 2026-03-24 |

## Completed

| # | Task | Completed | Created |
|---|------|-----------|---------|
| 1 | Short description | 2026-03-24 | 2026-03-20 |
```

## Task Lifecycle

### Creating a task
**Always do ALL of these steps, in order, before doing any actual work:**

1. Assign the next available `#` (incrementing integer, never reuse)
2. Create the task directory: `tasks/<YYYY-MM-DD>-<slug>/`
3. Create `tasks/<YYYY-MM-DD>-<slug>/README.md` with:
   - **What:** Clear description of what needs to be done
   - **Why:** Context or motivation (if provided)
   - **Acceptance criteria:** How do we know it's done?
   - **Plan:** Step-by-step plan for how to complete this task (numbered steps, specific and actionable)
   - **Notes:** Any relevant links, people, details
4. Add a row to the **Open** table in `TASKS.md`
5. Commit and push

The task folder and README with plan must exist BEFORE any work begins. This is non-negotiable — it ensures every task is documented and trackable from the start.

### Updating a task
1. Update the **Status** and **Last Updated** columns in `TASKS.md`
2. Add notes to the task's `README.md`
3. Commit and push

### Completing a task
1. Move the row from **Open** to **Completed** in `TASKS.md` with completion date
2. Add a completion summary to the task's `README.md`
3. Commit and push

### Archiving (monthly)
At the start of each month, move completed tasks older than 30 days:
1. Move their directories to `archive/YYYY-MM/`
2. Remove them from the **Completed** table in `TASKS.md`
3. Add a one-line entry to `archive/YYYY-MM/index.md`

## Conventions

- **Priorities:** 🔴 urgent (do today), 🟡 important (do this week), 🟢 nice-to-have
- **Statuses:** 📋 todo (not started), 🚧 wip (in progress), ⏳ blocked (waiting on something), ✅ done
- **Slugs:** lowercase, hyphens, max 40 chars (e.g., `buy-domain-for-paigong`)
- **Dates:** always YYYY-MM-DD format
- **Due dates:** optional. If not specified, leave blank.
- **Commits:** every task create/update/complete should be committed and pushed immediately
- **Always push** after any change so the GitHub repo stays current

## Working on Tasks

When Shawn asks you to work on a task:
1. Mark it 🚧 wip in `TASKS.md`
2. Do the work (may involve other repos, web searches, file creation, etc.)
3. Log what you did in the task's `README.md`
4. Mark it ✅ done and move to Completed
5. Commit and push

When Shawn shares something to do via Telegram or chat:
1. Create the task immediately (even if you'll work on it right away)
2. This ensures nothing gets lost

## Helpful Behaviors

- If a task has been 🚧 wip for more than 3 days, flag it
- If a 🔴 urgent task exists, mention it at the start of every conversation
- When creating tasks from vague requests, ask clarifying questions about priority and due date
- Proactively suggest breaking large tasks into subtasks
- When completing a task, ask if there are follow-up tasks to create
