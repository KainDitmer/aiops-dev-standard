# Skill Scout - Claude Code Skills Discovery

Discover, evaluate, and install Claude Code skills from curated repositories.

## Triggers

Use this skill when user asks to:
- Find new Claude Code skills
- Discover skill repositories
- Get skill recommendations
- Install a skill from a repository
- Update skill sources
- Check what skills they have installed

Keywords: "skill-scout", "find skills", "discover skills", "skill recommendations", "install skill"

## Workflow

### Mode Detection

Parse the user's command to determine mode:

| Command | Mode |
|---------|------|
| `/skill-scout` | Full scan + recommendations |
| `/skill-scout --inventory` | List installed skills only |
| `/skill-scout --category <cat>` | Focus on specific category |
| `/skill-scout --update-sources` | Discover new repositories |
| `/skill-scout install <skill>` | Install a specific skill |

### Step 1: Inventory Check

Scan user's installed skills:

```bash
# List all skill directories
ls -la ~/.claude/skills/

# For each skill, read SKILL.md to get description
for dir in ~/.claude/skills/*/; do
  if [ -f "$dir/SKILL.md" ]; then
    echo "=== $(basename $dir) ==="
    head -20 "$dir/SKILL.md"
  fi
done
```

Output current inventory in table format:
```markdown
## Currently Installed Skills

| Skill | Category | Description |
|-------|----------|-------------|
| ... | ... | ... |
```

### Step 2: Source Scanning (if not --inventory only)

Read known sources from `references/sources.md`.

For top-priority repositories, use WebFetch to get current skill lists:
1. anthropics/skills (official)
2. sickn33/antigravity-awesome-skills (most complete)
3. VoltAgent/awesome-agent-skills (official team skills)

Extract:
- Skill names
- Categories
- Brief descriptions
- Repository links

### Step 3: Gap Analysis

Compare user's installed skills against available skills:

1. Categorize user's current skills using `references/categories.md`
2. Identify missing categories
3. Read user's CLAUDE.md to understand their work context
4. Match gaps to user's actual needs

### Step 4: Recommendations

Output recommendations in priority tiers:

```markdown
## Skill Recommendations

### 🔥 High Priority (Direct Match to Your Work)
| Skill | Source | Why Relevant |
|-------|--------|--------------|
| [name] | [repo] | [reason based on CLAUDE.md analysis] |

### 📌 Medium Priority (Useful Additions)
| Skill | Source | Why Relevant |
|-------|--------|--------------|

### 📚 Explore Later
| Skill | Source | Category |
|-------|--------|----------|
```

### Step 5: Installation (if install mode)

When user wants to install a skill:

1. **Locate**: Find skill in known repositories
2. **Preview**: Show SKILL.md content and any references
3. **Confirm**: Ask user to confirm installation
4. **Install**:
   ```bash
   mkdir -p ~/.claude/skills/<skill-name>/references
   # Write SKILL.md
   # Write any reference files
   ```
5. **Verify**: Confirm skill appears in `/skills` command

## Categories

Reference `references/categories.md` for full definitions:

1. **Architecture** - System design, ADRs, scalable patterns
2. **Business** - Growth, pricing, SEO, go-to-market
3. **Data & AI** - LLM apps, RAG, agents, observability
4. **Development** - Language mastery, framework patterns
5. **General** - Planning, documentation, writing
6. **Infrastructure** - DevOps, cloud, CI/CD
7. **Security** - AppSec, pentesting, vulnerability analysis
8. **Testing** - TDD, QA workflows
9. **Workflow** - Automation, orchestration

## Evaluation Criteria

When recommending skills, score based on:

1. **Relevance** (0-5): Match to user's CLAUDE.md and work context
2. **Quality** (0-5): Well-documented, clear instructions
3. **Maintenance** (0-5): Recent updates, active repository
4. **Completeness** (0-5): Has references, examples, clear triggers

Only recommend skills scoring 12+ total.

## Output Format

Always structure output as:

1. **Inventory Summary** - What user has
2. **Gap Analysis** - What categories are missing
3. **Recommendations** - Prioritized suggestions
4. **Next Steps** - How to install recommended skills

## References

- `references/sources.md` - All known skill repositories
- `references/categories.md` - Category definitions
- `references/evaluation-criteria.md` - Scoring rubric
- `references/my-skills-inventory.md` - Track user's installations
