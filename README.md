# 🌙 Nightcrew

**Memory upgrades and autonomous workflows for OpenClaw agents.**

These patterns turn your OpenClaw agent from a reactive assistant into an autonomous PM that ships while you sleep.

---

## The Story

I went to bed at 10pm.

Woke up to 12 commits, passing tests, and a new feature deployed.

My OpenClaw agent Atlas did the work. These are the patterns that made it possible.

---

## What's Here

This isn't a replacement for OpenClaw's base files. It's **additions** — patterns you paste into your workspace to unlock autonomous behavior.

| File | What It Adds |
|------|--------------|
| `memory-upgrade.md` | Persistent memory system (long-term + daily logs) |
| `heartbeat-behaviors.md` | Proactive check-ins and autonomous work patterns |
| `subagent-templates.md` | Specialized roles for parallel work (QA, Bug Fix, etc.) |
| `blocker-protocol.md` | "Try before asking" — builds real capability |
| `work-state-tracking.md` | Structured state files for cross-session continuity |

---

## Quick Start

1. **Pick what you need** — Start with `memory-upgrade.md`
2. **Add to your AGENTS.md or HEARTBEAT.md** — Paste the relevant sections
3. **Create the file structure** — `memory/` folder, state files, etc.
4. **Let it evolve** — These patterns grow with use

---

## The Patterns

### 1. Memory Upgrade

Your agent wakes up fresh each session. This system gives it continuity:

```
MEMORY.md              → Long-term (curated facts, preferences)
memory/YYYY-MM-DD.md   → Daily logs (raw session notes)
```

**Key rule:** If it's not written to a file, it doesn't exist.

### 2. Heartbeat Behaviors

Instead of waiting for instructions, your agent checks in periodically:

- Project status (builds, tests)
- Blockers to flag
- Work to continue
- Memory maintenance

### 3. Sub-Agent Templates

For complex work, spawn specialists:

```
Main Session (PM)
├── QA Engineer → finds bugs
├── Bug Fix Engineer → surgical fixes
└── Verification QA → confirms fixes
```

Each has bounded scope and predictable outputs.

### 4. Blocker Protocol

Before asking for help:

1. Check available tools
2. Check memory
3. Try it
4. THEN ask

Prevents learned helplessness.

### 5. Work State Tracking

Structured JSON for cross-session continuity:

```json
{
  "completedToday": ["feature X", "bug Y"],
  "blockedOn": ["waiting for API key"],
  "inProgress": "dashboard redesign"
}
```

---

## Installation

### Option 1: Copy sections you need

Open each `.md` file, copy relevant sections into your workspace files.

### Option 2: Clone and adapt

```bash
git clone https://github.com/Jacknelson6/nightcrew.git
```

Pick what works, leave what doesn't.

---

## Philosophy

> "Human roles shift from 'telling the agent what to do' to 'engineering conditions where good outcomes emerge naturally."

You're not micromanaging. You're building systems.

---

## Credits

Built by [@jackhnels](https://twitter.com/jackhnels) and Atlas, shipping products daily with [OpenClaw](https://openclaw.ai).

---

## License

MIT
