---
name: plan-review-workflow
description: Orchestrates the two-Claude pattern where plans are automatically reviewed by a staff engineer subagent before implementation. Use this workflow for any significant implementation - features, refactors, architectural changes.
---

# Plan Review Workflow

## Overview

Two-Claude pattern for quality assurance:
1. **Planning Agent** (you): Creates the implementation plan
2. **Staff Engineer Subagent**: Reviews with fresh eyes, separate context

This catches problems before implementation, not after.

## When to Use

Use this workflow when:
- Implementing a new feature
- Refactoring existing code
- Making architectural changes
- Any multi-file change
- Changes that could break existing functionality

Do NOT use for:
- Simple bug fixes (typos, obvious errors)
- Documentation-only changes
- Single-line changes

## Workflow Steps

### Step 1: Create Initial Plan

Create a detailed implementation plan with:

```markdown
## Problem Statement
[What problem are we solving? Why now?]

## Proposed Solution
[High-level approach]

## Implementation Steps
1. [Step with specific files/functions]
2. [Step with specific files/functions]
3. ...

## Files Affected
- `path/to/file.ts` - [what changes]
- `path/to/other.py` - [what changes]

## Testing Strategy
- [ ] Unit tests for [what]
- [ ] Integration tests for [what]
- [ ] Manual testing: [scenarios]

## Rollback Plan
[How to revert if this fails in production]

## Open Questions
- [Any uncertainties]
```

### Step 2: Staff Engineer Review

After creating the plan, ALWAYS invoke the staff-engineer subagent:

```
Use the Task tool with subagent_type "staff-engineer" to review this plan:
[your plan]
```

The subagent has a separate context and will provide objective feedback.

### Step 3: Process Feedback

Based on the review verdict:

| Verdict | Action |
|---------|--------|
| **APPROVED** | Proceed with implementation |
| **APPROVED WITH CHANGES** | Address critical issues, update plan, optionally re-review |
| **NEEDS REVISION** | Create new plan addressing all feedback, then re-submit |

### Step 4: Iterate if Needed

If NEEDS REVISION or APPROVED WITH CHANGES:
1. Update the plan based on feedback
2. Submit revised plan to staff-engineer subagent
3. Repeat until APPROVED

## Rules

- **Never skip the review step** - even if you think the plan is solid
- **Always address CRITICAL issues** - these are non-negotiable
- **Document disagreements** - if you're not incorporating feedback, explain why to the user
- **Maximum 3 iterations** - if still not approved, involve the user

## Integration with EnterPlanMode

When using Claude Code's plan mode:
1. Use EnterPlanMode to explore and create the plan
2. Before ExitPlanMode, spawn staff-engineer to review
3. Only exit plan mode after APPROVED verdict
