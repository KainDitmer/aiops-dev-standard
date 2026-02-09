# Plan & Review Workflow for Claude Code

A two-Claude pattern that automatically reviews your implementation plans before you start coding. A "staff engineer" subagent reviews your plan with fresh eyes, catches edge cases, and prevents over-engineering.

## What It Does

1. You type `/plan-and-review add user authentication`
2. Claude creates a detailed implementation plan
3. A separate Claude instance (staff engineer) reviews the plan critically
4. Feedback is incorporated, the plan iterates until approved
5. You get an approved, battle-tested plan before writing a single line of code

You can also use `/staff-engineer` standalone to review any plan you've already written.

## Installation

Copy `agents/`, `commands/`, and `skills/` into your project's `.claude/` directory:

```bash
# Copy skill directories into your project's .claude/:
cp -r agents commands skills /path/to/your-project/.claude/

# If .claude/ already has these subdirs, merge instead:
rsync -a agents/ /path/to/your-project/.claude/agents/
rsync -a commands/ /path/to/your-project/.claude/commands/
rsync -a skills/ /path/to/your-project/.claude/skills/
```

The commands and skills are automatically picked up by Claude Code.

## What's Included

```
plan-and-review/
├── INDEX.md
├── README.md
├── agents/
│   └── staff-engineer.md     # Staff engineer agent definition
├── commands/
│   ├── plan-and-review.md    # /plan-and-review slash command
│   └── staff-engineer.md     # /staff-engineer slash command
└── skills/
    ├── plan-review-workflow/
    │   └── SKILL.md           # Orchestration logic
    └── staff-engineer-review/
        └── SKILL.md           # Review prompt & checklist
```

## Usage

### Full workflow (plan + automatic review)
```
/plan-and-review implement a caching layer for the API
```

### Review an existing plan
```
/staff-engineer [paste your plan here]
```

### How the review works

The staff engineer checks for:
- **Edge cases**: null values, race conditions, network failures
- **Faulty assumptions**: implicit dependencies, environment assumptions
- **Over-engineering**: unnecessary abstractions, too many files
- **Performance risks**: N+1 queries, unbounded loops
- **Security**: input validation, auth checks, data exposure

Each review ends with a verdict:

| Verdict | What happens |
|---------|-------------|
| **APPROVED** | Plan is solid, proceed with implementation |
| **APPROVED WITH CHANGES** | Fix critical issues first, then proceed |
| **NEEDS REVISION** | Significant rework needed, plan iterates |

Maximum 3 iterations before asking you for guidance.

## Requirements

- Claude Code CLI
- Works with any tech stack (the review is architecture-agnostic)
- The staff engineer subagent uses the `opus` model for best results

## Tips

- Works best for multi-file changes, new features, and refactors
- Skip it for single-line fixes or typos
- The staff engineer is intentionally skeptical - that's the point
