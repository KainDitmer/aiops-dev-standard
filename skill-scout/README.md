# Skill Scout - Claude Code Skills Discovery

Discover, evaluate, and install Claude Code skills from curated repositories.

## What It Does

1. Scans your installed skills (project-level and user-level)
2. Fetches available skills from curated repositories
3. Analyzes gaps based on your project context
4. Recommends skills ranked by relevance, quality, and completeness

## Installation

Copy the skill into your project's `.claude/skills/` directory:

```bash
mkdir -p /path/to/your-project/.claude/skills/skill-scout
cp SKILL.md /path/to/your-project/.claude/skills/skill-scout/
cp -r references /path/to/your-project/.claude/skills/skill-scout/
```

## Usage

```
/skill-scout                        # Full scan + recommendations
/skill-scout --inventory            # List installed skills only
/skill-scout --category <cat>       # Focus on specific category
/skill-scout --update-sources       # Discover new repositories
/skill-scout install <skill>        # Install a specific skill
```

## Requirements

- Claude Code CLI
- Internet access (for fetching repository data)
