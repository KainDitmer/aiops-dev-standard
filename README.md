# aiops-dev-standard

Experimental Claude Code skills and workflows built by the AIOps community to help you build cool stuff faster. Each subdirectory is a self-contained skill package — see per-package install instructions below.

## Installation

### plan-and-review

Copy `agents/`, `commands/`, and `skills/` into your project's `.claude/`:

```bash
cd plan-and-review && cp -r agents commands skills /path/to/your-project/.claude/
```

### skill-scout

Copy into `.claude/skills/skill-scout/`:

```bash
mkdir -p /path/to/your-project/.claude/skills/skill-scout
cp skill-scout/SKILL.md /path/to/your-project/.claude/skills/skill-scout/
cp -r skill-scout/references /path/to/your-project/.claude/skills/skill-scout/
```

## Structure

- `plan-and-review/` — Two-Claude plan review workflow (staff engineer subagent reviews plans before implementation)
- `skill-scout/` — Skills discovery and installation tool for finding Claude Code skills from curated repositories

## Community Resources

### Skills & Collections
- [anthropics/skills](https://github.com/anthropics/skills) — Official Anthropic skills (docx, pdf, pptx, xlsx conversion)
- [sickn33/antigravity-awesome-skills](https://github.com/sickn33/antigravity-awesome-skills) — Largest collection (626+ skills, 9 categories)
- [VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills) — Production-ready integrations (Vercel, Stripe, Supabase)
- [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) — Curated quality picks
- [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) — Skills + hooks + plugins ecosystem
- [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) — SaaS integrations (Gmail, Slack, Calendar)
- [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) — Production-ready, modular skills
- [daymade/claude-code-skills](https://github.com/daymade/claude-code-skills) — Marketplace-style skill collection

### MCP & Tools
- [vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser) — Browser automation CLI for AI agents

### Security
- [KeygraphHQ/shannon](https://github.com/KeygraphHQ/shannon) — Autonomous AI security testing for web apps

### Setup & Configuration
- [solatis/claude-config](https://github.com/solatis/claude-config) — Claude Code customizations and config reference

### Learning & Patterns
- [coleam00/context-engineering-intro](https://github.com/coleam00/context-engineering-intro) — Context engineering patterns
- [OneRedOak/claude-code-workflows](https://github.com/OneRedOak/claude-code-workflows) — Code/Security/Design review workflows
