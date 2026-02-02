# 🌙 Nightcrew

**Turn Claude into an autonomous PM that ships code while you sleep.**

Memory systems, sub-agent patterns, and proactive workflows for [OpenClaw](openclaw.ai)

---

## What is this?

Nightcrew is a collection of markdown templates and patterns that transform Claude from a reactive assistant into a proactive development partner. Instead of waiting for instructions, Claude:

- **Remembers context** across sessions using structured memory files
- **Works autonomously** on tasks using sub-agent patterns
- **Checks in proactively** via heartbeats when there's work to do
- **Ships code** while you're away (gym, meetings, sleep)

These patterns emerged from months of daily collaboration building SaaS products, automating workflows, and shipping features.

---

## Quick Start

### Option 1: Copy-paste into your workspace

1. Create these files in your Claude workspace:
   - `AGENTS.md` — Operational guide (how Claude should behave)
   - `HEARTBEAT.md` — Proactive check-in behaviors
   - `MEMORY.md` — Long-term memory storage
   - `memory/` folder — Daily logs

2. Copy the templates from this repo into those files.

3. Start a conversation with Claude and reference the files.

### Option 2: Clone and customize

```bash
git clone https://github.com/Jacknelson6/nightcrew.git
cd nightcrew
# Customize the templates for your needs
# Move to your Claude workspace
```

---

## The Files

| File | Purpose |
|------|---------|
| `AGENTS.md` | Core operational guide — tells Claude how to behave, when to act vs. ask, safety boundaries |
| `HEARTBEAT.md` | Proactive behaviors — what to check during idle time, when to reach out |
| `MEMORY.md` | Long-term memory template — facts, preferences, lessons learned |
| `SUBAGENTS.md` | Sub-agent prompt templates — specialized roles for parallel work |
| `memory/YYYY-MM-DD.md` | Daily log template — raw session notes |

---

## Core Concepts

### 1. Memory Persistence

Claude wakes up fresh each session. These files ARE its memory:

```
MEMORY.md          → Long-term (curated facts, preferences, lessons)
memory/2024-01-15.md → Daily logs (raw notes from each session)
```

**Key insight:** If you want Claude to remember something, it must be written to a file. "Mental notes" don't survive restarts.

### 2. Proactive Heartbeats

Instead of only responding when prompted, Claude can check in periodically:

- Check project status
- Run builds/tests
- Review memory files
- Flag blockers or completed work

Configure a heartbeat interval (e.g., every 15-30 min) and Claude will use `HEARTBEAT.md` to decide what needs attention.

### 3. Sub-Agent Patterns

For complex tasks, spawn specialized sub-agents:

- **QA Engineer** — Tests flows, finds bugs
- **Bug Fix Engineer** — Surgical fixes without refactoring
- **Frontend/Backend Engineer** — Domain-specific implementation

Each sub-agent has bounded expertise and predictable outputs. The main session acts as PM, coordinating work.

### 4. Blocker Protocol

Before asking for help, Claude should:

1. Check available tools
2. Check memory for prior solutions
3. Try to solve it
4. Only then ask

This prevents learned helplessness and builds genuine capability.

---

## Example Workflow

**You (9 PM):** "I'm going to bed. Keep working on the dashboard. Ping me on Telegram if you hit blockers."

**Claude:**
1. Reviews `HEARTBEAT.md` for priorities
2. Spawns sub-agent to implement next feature
3. Runs QA pass when feature completes
4. Commits and pushes
5. Updates `memory/2024-01-15.md` with progress
6. Checks in via heartbeat — nothing blocked, continues
7. Repeats until done or blocked

**You (7 AM):** Wake up to commits, passing tests, and a status summary.

---

## Customization

These templates are starting points. Customize for your:

- **Projects** — Add project-specific context to MEMORY.md
- **Tools** — Document CLI tools, API keys, credentials in AGENTS.md
- **Preferences** — Communication style, working hours, alert thresholds
- **Workflows** — Your specific deployment, testing, review processes

---

## Philosophy

> "Human roles shift from 'telling the agent what to do' to 'engineering conditions where good outcomes emerge naturally through iteration."

The goal isn't to micromanage Claude. It's to set up systems where:

- Context persists across sessions
- Work continues without constant direction
- Quality is maintained through automated checks
- You're only interrupted when necessary

---

## Credits

Built by [@jackhnelson](https://twitter.com/jackhnelson) and Atlas (Claude) through daily collaboration shipping products.

Inspired by [Ralph Loops](https://ghuntley.com/ralph/) by Geoffrey Huntley.

---

## License

MIT — Use freely, modify as needed, share with others.
