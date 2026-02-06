# Skill Evaluation Criteria

## Scoring Rubric

Each skill is evaluated on 4 dimensions, scored 0-5.
**Minimum score for recommendation: 12/20**

---

## 1. Relevance (0-5)

How well does this skill match the user's work context?

| Score | Criteria |
|-------|----------|
| 5 | Direct match to user's tech stack AND current work |
| 4 | Matches tech stack, generally useful |
| 3 | Related to user's domain |
| 2 | Tangentially related |
| 1 | Different domain but transferable |
| 0 | Not relevant to user's work |

**Signals to check**:
- Match against CLAUDE.md keywords
- Tech stack alignment (languages, frameworks)
- Domain alignment (web dev, data, etc.)

---

## 2. Quality (0-5)

How well-documented and structured is the skill?

| Score | Criteria |
|-------|----------|
| 5 | Clear triggers, detailed workflow, examples, references |
| 4 | Good documentation, clear workflow |
| 3 | Adequate documentation, usable |
| 2 | Sparse documentation, requires guessing |
| 1 | Minimal documentation |
| 0 | No documentation or broken |

**Check for**:
- Clear trigger keywords
- Step-by-step workflow
- Example invocations
- Reference files (if complex)

---

## 3. Maintenance (0-5)

Is the skill actively maintained?

| Score | Criteria |
|-------|----------|
| 5 | Updated within 30 days, active repo |
| 4 | Updated within 90 days |
| 3 | Updated within 6 months |
| 2 | Updated within 1 year |
| 1 | No updates in 1+ year |
| 0 | Abandoned or archived |

**Check for**:
- Last commit date
- Open issues / PRs
- Repository activity
- For aggregators: individual skill dates

---

## 4. Completeness (0-5)

Does the skill have everything needed to be useful?

| Score | Criteria |
|-------|----------|
| 5 | SKILL.md + references + examples + tests |
| 4 | SKILL.md + references |
| 3 | SKILL.md with detailed instructions |
| 2 | Basic SKILL.md |
| 1 | Partial SKILL.md |
| 0 | Missing critical components |

**Required components**:
- SKILL.md with clear instructions
- Trigger keywords
- Workflow steps
- (Bonus) Reference files
- (Bonus) Example outputs

---

## Priority Tiers

Based on total score:

| Tier | Score | Recommendation |
|------|-------|----------------|
| 🔥 High Priority | 16-20 | Install immediately |
| 📌 Medium Priority | 12-15 | Worth installing |
| 📚 Explore Later | 8-11 | Keep for future |
| ❌ Skip | 0-7 | Don't recommend |

---

## Quick Evaluation Checklist

For rapid assessment during scanning:

```markdown
□ Has SKILL.md? (required)
□ Clear triggers defined?
□ Workflow steps documented?
□ Matches user's tech stack?
□ Updated recently (< 6 months)?
□ Has references/examples?
```

**Quick score**:
- 6 checks = High Priority
- 4-5 checks = Medium Priority
- 2-3 checks = Explore Later
- 0-1 checks = Skip

---

## Source Quality Multiplier

Adjust scores based on source reputation:

| Source | Multiplier |
|--------|------------|
| anthropics/skills | 1.2x |
| antigravity-awesome-skills | 1.1x |
| VoltAgent/awesome-agent-skills | 1.1x |
| travisvn/awesome-claude-skills | 1.0x |
| Other curated lists | 1.0x |
| Individual repos | 0.9x |

---

## Example Evaluation

```markdown
Skill: `pytest-expert`
Source: antigravity-awesome-skills

Relevance: 5/5
- User's CLAUDE.md mentions pytest explicitly
- Python backend project

Quality: 4/5
- Clear triggers
- Good workflow
- No examples in skill itself

Maintenance: 4/5
- Updated 2 months ago
- Part of active collection

Completeness: 3/5
- SKILL.md only
- No reference files

Raw Score: 16/20
Source Multiplier: 1.1x
Final Score: 17.6

Recommendation: 🔥 High Priority
```
