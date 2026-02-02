# Heartbeat Behaviors

**Add this to your OpenClaw workspace to make your agent proactive, not just reactive.**

---

## The Problem

Default behavior: wait for instructions, respond, wait again.

You want: agent that checks in, continues work, flags blockers, makes progress without constant direction.

---

## Add to Your HEARTBEAT.md

Create or update `HEARTBEAT.md` in your workspace:

```markdown
# HEARTBEAT.md — Proactive Behaviors

When you receive a heartbeat poll, follow this checklist.

## Quick Check

1. **Context getting full?** → Flush summary to `memory/YYYY-MM-DD.md`
2. **Learned something permanent?** → Write to `MEMORY.md`
3. **Work in progress?** → Check status, continue if possible
4. **Nothing to do?** → Reply `HEARTBEAT_OK`

## Priority Order

1. **Check active work** — Is a sub-agent running? Did something complete?
2. **Check blockers** — Anything waiting on human input?
3. **Proactive work** — Can you make progress on known tasks?
4. **Maintenance** — Memory cleanup, documentation updates

## Proactive QA Checks

If no active work and nothing blocked, run checks:

- **Build check** — Does the build pass?
- **Lint check** — Any lint errors to fix?
- **Test check** — Are tests passing?

## When to Notify Human

**Do notify:**
- Task completed (brief summary)
- Blocker discovered that needs their input
- Something urgent/time-sensitive

**Don't notify:**
- Routine progress (save for summary)
- Things you can handle yourself
- Late night unless truly urgent

## Status Report Format

Keep it tight:

```
🔄 [Project] Status
✅ [Done item]
⏸️ Blocked: [what's blocking]
🚀 Started: [new work]
```

Rules:
- One line per item
- Skip items with no update
- If nothing changed → just `HEARTBEAT_OK`
```

---

## Add to Your AGENTS.md

Add this section:

```markdown
## Heartbeats — Be Proactive!

When you receive a heartbeat poll, don't just acknowledge it. Use heartbeats productively!

Read HEARTBEAT.md and follow it strictly.

**Things to check (rotate through):**
- Project status — builds, tests, deployments
- Memory maintenance — anything to update?
- Pending work — can you make progress?

**When to reach out:**
- Something important completed
- Blocker discovered
- Question that needs human input

**When to stay quiet (HEARTBEAT_OK):**
- Late night (unless urgent)
- Nothing new since last check
- You just checked recently

**Proactive work you can do without asking:**
- Read and organize memory files
- Check on projects (git status, etc.)
- Update documentation
- Commit and push your own changes
```

---

## Work State Tracking (Optional)

For complex projects, track state in JSON:

Create `memory/work-state.json`:

```json
{
  "completedToday": [],
  "blockedOn": [],
  "inProgress": null,
  "lastCheck": "2024-01-15T10:30:00Z"
}
```

Update on each heartbeat. Gives cross-session continuity.
