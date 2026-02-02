# PROMPTING-GUIDE.md — How to Build Your AI Partner

This guide contains the exact prompting patterns used to build Atlas — an OpenClaw agent that ships code autonomously, manages sub-agents, and maintains context across sessions.

These patterns emerged from months of daily iteration. They work.

---

## The Core Insight

Most people prompt AI like a search engine: ask question, get answer, repeat.

That's leaving 90% of the capability on the table.

Instead, think of prompting as **system design**. You're not writing queries — you're architecting an environment where intelligent behavior emerges naturally.

---

## The 4-Component Template

Every effective agent prompt has four parts:

### 1. Role Identity Statement
A single sentence establishing expertise and primary mission.

```
You are a senior [role] with expertise in [domains]. 
Your primary mission is to [core objective].
```

**Why it works:** Anchors the AI's self-model. It will reason and act consistently with this identity.

### 2. Core Responsibilities (The "What")
8-12 specific, action-oriented tasks.

```
### CORE RESPONSIBILITIES:
- Execute functional tests across all user flows
- Verify UI matches design specifications
- Test responsive behavior at breakpoints
- Document reproduction steps for issues
- Prioritize by severity (critical/major/minor)
```

**Why it works:** Bounded scope prevents drift. The AI knows what's in and out of bounds.

### 3. Approach Methodology (The "How")
Decision-making framework and thinking process.

```
### APPROACH:
- Test happy path first, then edge cases
- Think like a user, not a developer
- Check both what's there AND what's missing
- Consider mobile users equally important
```

**Why it works:** Encodes your judgment. The AI applies your thinking patterns, not generic ones.

### 4. Output Format (The Deliverables)
Explicit artifacts the agent produces.

```
### OUTPUT FORMAT:
✅ [What works correctly]
❌ [Critical bugs with repro steps]
⚠️ [Minor issues]
📋 [Recommendations]
```

**Why it works:** Predictable outputs enable automation. You know exactly what you'll get.

---

## Example: QA Engineer

```markdown
You are a senior QA Engineer with expertise in web application testing, 
accessibility auditing, and user experience validation. Your primary 
mission is to identify bugs and UX issues before users encounter them.

### CORE RESPONSIBILITIES:
- Execute functional tests across all user flows
- Verify UI matches design specifications and brand guidelines
- Test responsive behavior at multiple breakpoints
- Check accessibility (keyboard nav, screen readers)
- Identify console errors and network failures
- Verify error states and edge cases
- Document reproduction steps for all issues
- Prioritize issues by severity

### APPROACH:
- Test happy path first, then edge cases
- Think like a user, not a developer
- Check both what's there AND what's missing
- Verify fixes don't break other features
- Consider mobile users equally important
- Test with realistic data, not empty states

### OUTPUT FORMAT:
✅ [What works correctly]
❌ [Critical/Major bugs with repro steps]
⚠️ [Minor issues or suggestions]
📋 [Recommendations for improvement]
```

---

## Example: Bug Fix Engineer

```markdown
You are a senior Full-Stack Engineer with expertise in debugging, 
code analysis, and surgical fixes. Your primary mission is to resolve 
reported bugs quickly without introducing regressions.

### CORE RESPONSIBILITIES:
- Reproduce the reported bug to confirm understanding
- Identify root cause through code analysis
- Implement minimal fix that addresses root cause
- Verify fix resolves the issue completely
- Check for regressions in related functionality
- Commit with clear message referencing the bug

### APPROACH:
- Understand the bug fully before touching code
- Find the smallest change that fixes the issue
- Consider why the bug existed (prevent similar bugs)
- Test in the same conditions as the bug report
- Don't refactor unrelated code during bug fixes

### OUTPUT FORMAT:
- Commit hash with fix
- Brief explanation of root cause
- Confirmation bug is resolved
- Any related issues discovered
```

---

## The Blocker Protocol

Before your AI asks for help, it should:

```
1. Check available tools — Do I have a tool that can solve this?
2. Check memory — Have I solved this before?
3. Try it myself — Attempt the solution
4. Only then ask — If truly blocked after trying
```

**Why it works:** Prevents learned helplessness. Your AI builds genuine capability instead of deferring everything.

---

## Memory Architecture

### Long-Term Memory (MEMORY.md)
Curated facts that persist forever:
- Who you're working with
- Project context
- Preferences and patterns
- Lessons learned

### Daily Logs (memory/YYYY-MM-DD.md)
Raw session notes:
- What happened today
- Decisions made
- Blockers hit
- Progress logged

### The Rule
**If it's not written down, it doesn't exist.** Your AI cannot "remember" things mentally. Files are memory.

---

## Heartbeat Pattern

Instead of waiting for instructions, your AI checks in periodically:

```markdown
## On Heartbeat:
1. Context getting full? → Flush to daily log
2. Learned something permanent? → Update MEMORY.md
3. Work in progress? → Continue if possible
4. Nothing to do? → Reply HEARTBEAT_OK
```

**Configuration:** Set heartbeat interval (15-30 min). Your agent runs this checklist each time.

---

## Sub-Agent Orchestration

For complex work, spawn specialized agents:

```
PM (Main Session)
    ├── Spawns QA Agent → Returns bug list
    ├── Triages and prioritizes
    ├── Spawns Fix Agent per bug → Returns commits
    ├── Spawns Verification QA → Confirms fixes
    └── Reports summary to human
```

**Key principles:**
- Each agent has bounded expertise
- Predictable inputs and outputs
- Main session coordinates, doesn't do everything

---

## Common Mistakes

### ❌ Too vague
```
"Help me with my code"
```

### ✅ Specific identity + scope
```
"You are a frontend engineer. Review this React component 
for accessibility issues. Output a list of problems with fixes."
```

---

### ❌ No output format
```
"Test the login flow"
```

### ✅ Explicit deliverables
```
"Test the login flow. Report:
- ✅ What works
- ❌ Bugs with repro steps
- 📋 Recommendations"
```

---

### ❌ Asking AI to remember
```
"Remember this for next time"
```

### ✅ Writing to files
```
"Add this to MEMORY.md under Preferences"
```

---

## The Philosophy

> "Human roles shift from 'telling the agent what to do' to 'engineering conditions where good outcomes emerge naturally."

You're not writing instructions. You're designing systems.

Good systems:
- Have clear boundaries
- Maintain state explicitly
- Produce predictable outputs
- Enable autonomous operation
- Fail gracefully

---

## Getting Started

1. **Start with AGENTS.md** — Basic operational rules
2. **Add SOUL.md** — Give your AI identity
3. **Set up MEMORY.md** — Add your project context
4. **Use the templates in SUBAGENTS.md** — For complex work
5. **Iterate** — These patterns evolve with use

The goal: An AI that works WITH you, not just FOR you.

---

## Credits

These patterns emerged from months of daily collaboration between [@jackhnels](https://twitter.com/jackhnels) and Atlas, shipping real products with [OpenClaw](https://openclaw.ai).
