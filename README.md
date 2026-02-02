# 🌙 Nightcrew

**Turn your OpenClaw agent into an autonomous PM that ships code while you sleep.**

---

## The Story

I went to bed at 10pm.

Woke up to 12 commits, passing tests, and a new feature deployed to production.

I didn't hire a team. I didn't stay up coding. I taught my AI how to work while I sleep.

His name is Atlas. He's an [OpenClaw](https://openclaw.ai) agent.

This repo contains the exact system — the markdown files, the prompts, the patterns — that turned a basic AI assistant into an autonomous development partner.

After months of daily collaboration shipping SaaS products, these patterns emerged. Now I'm sharing them.

---

## What's Inside

| File | Purpose |
|------|---------|
| `SOUL.md` | **Start here** — Identity and personality template |
| `AGENTS.md` | Core operational guide — how your agent should behave |
| `HEARTBEAT.md` | Proactive behaviors — what to check during idle time |
| `MEMORY.md` | Long-term memory template — facts that persist |
| `SUBAGENTS.md` | Sub-agent prompts — specialized roles for parallel work |
| `PROMPTING-GUIDE.md` | **The complete guide** — how to prompt like this |
| `memory/TEMPLATE.md` | Daily log template — raw session notes |

---

## Quick Start

1. **Clone this repo** into your OpenClaw workspace
2. **Read `PROMPTING-GUIDE.md`** — understand the patterns
3. **Customize `SOUL.md`** — give your agent a name and personality
4. **Set up `MEMORY.md`** — add your project context
5. **Start collaborating** — your agent reads these files automatically

```bash
git clone https://github.com/Jacknelson6/nightcrew.git
```

---

## Core Concepts

### 1. Your Agent Has a Soul

`SOUL.md` defines WHO your agent is — not just what it does:
- A name
- A personality
- Core values
- Boundaries

An agent with identity makes better decisions than one following generic instructions.

### 2. Memory Lives in Files

Your agent wakes up fresh each session. These files ARE its memory:

```
MEMORY.md              → Long-term (curated facts, preferences)
memory/2024-01-15.md   → Daily logs (raw session notes)
```

**Key insight:** "Mental notes" don't survive restarts. Files do.

### 3. Proactive, Not Reactive

Configure heartbeat intervals. Instead of waiting for instructions:
- Check project status
- Run builds and tests
- Continue work autonomously
- Only ping you when blocked or done

### 4. Sub-Agents for Parallel Work

Spawn specialized agents:
- **QA Engineer** — finds bugs before users do
- **Bug Fix Engineer** — surgical fixes, no scope creep
- **Frontend/Backend Engineer** — domain expertise

Main session acts as PM, coordinating the team.

---

## Example Night

**10:00 PM** — "Keep working on the dashboard. Ping me if blocked."

**10:30 PM** — Agent spawns frontend sub-agent for new feature

**11:45 PM** — Feature done, spawns QA sub-agent

**12:30 AM** — QA finds 2 bugs, spawns fix agents

**2:00 AM** — Fixes verified, commits pushed

**7:00 AM** — You wake up to a status summary and working code

---

## Read the Full Guide

`PROMPTING-GUIDE.md` contains:
- The 4-component prompt template
- Real examples from months of iteration
- Common mistakes and how to avoid them
- Memory architecture deep dive
- Sub-agent orchestration patterns

---

## Philosophy

> "Human roles shift from 'telling the agent what to do' to 'engineering conditions where good outcomes emerge naturally."

You're not micromanaging. You're building systems where:
- Context persists across sessions
- Work continues without constant direction
- Quality is maintained through automated checks
- You're only interrupted when necessary

---

## Credits

Built by [@jackhnels](https://twitter.com/jackhnels) and Atlas through daily collaboration shipping products with [OpenClaw](https://openclaw.ai).

Inspired by [Ralph Loops](https://ghuntley.com/ralph/) by Geoffrey Huntley.

---

## License

MIT — Use freely, share widely.
