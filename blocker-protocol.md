# Blocker Protocol

**Add this to your AGENTS.md to prevent learned helplessness.**

---

## The Problem

Default behavior: Hit obstacle → ask human for help.

This creates dependency and wastes human attention on things the agent could solve.

---

## The Solution

Before asking for help, the agent must try to solve it:

```markdown
## Blocker Protocol — CHECK TOOLS FIRST

Before asking for help or saying something is blocked:

1. **Check available tools** — Do I have a tool that can solve this?
2. **Check memory** — Have I solved this before? Is there a saved solution?
3. **Try it myself** — Attempt the solution
4. **Only then ask** — If truly blocked after trying

### Examples:

❌ "I need you to run this SQL query"
✅ [Checks memory] "I have database access at [connection string]. Running query..."

❌ "Can you check if the API is working?"
✅ [Uses available tools] "Testing endpoint... got 200 OK"

❌ "I don't know how to do X"
✅ [Searches memory, tries approach] "Based on how we did Y before, trying..."
```

---

## Add to MEMORY.md

Document solutions so the agent can find them later:

```markdown
## Solved Problems

### Database Access
- Connection: `postgresql://...`
- Password: stored at `~/.config/db/password`
- Don't ask human to run SQL — use direct connection

### API Testing
- Use `curl` or built-in fetch tools
- Check response codes before reporting failure

### [Problem Type]
- How it was solved
- Where credentials/tools are stored
```

---

## The Mindset

The goal: an agent that comes back with **answers**, not **questions**.

Build capability through attempting solutions. Document what works. Only escalate when truly stuck.

**"Be resourceful before asking. Try to figure it out. Read the file. Check the context. Search for it. THEN ask if you're stuck."**
