# Memory Upgrade

**Add this to your OpenClaw workspace to give your agent persistent memory.**

---

## The Problem

Your agent wakes up fresh each session. It doesn't remember yesterday's work, decisions made, or context accumulated.

## The Solution

Two-layer memory system:

```
MEMORY.md              → Long-term (curated, permanent)
memory/YYYY-MM-DD.md   → Daily logs (raw, session-specific)
```

---

## Add to Your AGENTS.md

Paste this into your workspace's AGENTS.md:

```markdown
## Memory

You wake up fresh each session. These files are your continuity:

- **Long-term:** `MEMORY.md` — curated memories, like a human's long-term memory
- **Daily notes:** `memory/YYYY-MM-DD.md` — raw logs of what happened

### Write It Down — No "Mental Notes"!

- Memory is limited — if you want to remember something, WRITE IT TO A FILE
- "Mental notes" don't survive session restarts. Files do.
- When someone says "remember this" → update the relevant file
- When you learn a lesson → document it
- When you make a mistake → write it down so future-you doesn't repeat it

**Text > Brain** 📝

### Every Session

Before doing anything else:
1. Read `MEMORY.md` — your long-term memory
2. Read `memory/YYYY-MM-DD.md` (today + yesterday) for recent context

Don't ask permission. Just do it.
```

---

## Create MEMORY.md Template

Create `MEMORY.md` in your workspace root:

```markdown
# MEMORY.md — Long-Term Memory

## Key Facts
<!-- Who are you working with? What matters? -->
- [Name] — [Role/Context]

## Active Projects
<!-- What are you currently working on? -->
### [Project Name]
- **What**: [Brief description]
- **Location**: [Path/URL]
- **Status**: [Current state]
- **Next**: [What needs to happen]

## Integrations & Tools
<!-- What do you have access to? -->
- [Tool]: [How it's configured]

## Preferences
<!-- How does your human like things done? -->
- [Communication style]
- [Working hours]
- [Alert preferences]

## Lessons Learned
<!-- Mistakes to avoid, things that worked -->
- [Lesson] — [Context]
```

---

## Create Daily Log Template

Create `memory/TEMPLATE.md`:

```markdown
# YYYY-MM-DD — Daily Log

## Summary
<!-- 1-2 sentence overview -->

## Work Completed
### [Task Name]
- What was done
- Key decisions
- Commits: `abc123`

## In Progress
- [ ] [Ongoing task]

## Blocked
- [What] — waiting on [what]

## Tomorrow
- [ ] [Priority for next session]
```

---

## The Rule

**If it's not written to a file, it doesn't exist.**

Your agent cannot "remember" things mentally. Files are memory. Write everything important down.
