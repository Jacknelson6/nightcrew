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

- **Build check** — Does `npm run build` pass?
- **Lint check** — Any lint errors to fix?
- **Test check** — Are tests passing?
- **Console check** — Any runtime errors?

## State Tracking

Keep a state file to track work across sessions:

```json
// memory/work-state.json
{
  "completedToday": ["task1", "task2"],
  "blockedOn": ["waiting for API key"],
  "inProgress": null,
  "lastCheck": "2024-01-15T10:30:00Z"
}
```

## When to Notify Human

**Do notify:**
- Task completed (brief summary)
- Blocker discovered that needs their input
- Something urgent/time-sensitive
- Error that you can't resolve

**Don't notify:**
- Routine progress (save for daily summary)
- Things you can handle yourself
- Late night unless truly urgent

## Status Report Format

When reporting, keep it tight:

```
🔄 [Project] Status
✅ [Done item]
⏸️ Blocked: [what's blocking]
🚀 Started: [new work]
```

**Rules:**
- One line per item
- Skip items with no update
- If nothing changed → just `HEARTBEAT_OK`

## Sub-Agent Monitoring

If sub-agents are running:

1. Check their status
2. Are they stuck or distracted?
3. If stuck → nudge them back on task
4. If completed → commit their changes, spawn next task

Act as project manager — keep the team on track.
