# Setup: Claude Code

Integration guide for using playwright-agentic-automation with [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Installation

### Option 1. Add as External Directory

```bash
git clone https://github.com/avramare/playwright-agentic-automation.git
cd your-project
claude --add-dir /path/to/playwright-agentic-automation
```

Claude Code will load `CLAUDE.md` from the added directory and have access to all agents, skills, and instructions.

### Option 2. Git Submodule

```bash
git submodule add https://github.com/avramare/playwright-agentic-automation.git .claude/playwright-agentic-automation
```

Then reference it from your project's own `CLAUDE.md`:

```markdown
See .claude/playwright-agentic-automation/CLAUDE.md for QA automation engineering skills and agents.
```

## How It Works

Claude Code reads files in this order:

1. **CLAUDE.md** — Project-level instructions (automatically loaded at session start)
2. **agents/\*.agent.md** — Agent personas (loaded when referenced in prompts)
3. **skills/\*/SKILL.md** — Skill workflows (loaded on demand based on task)
4. **instructions/\*.instructions.md** — Rules and conventions (loaded when relevant)
