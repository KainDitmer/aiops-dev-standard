# Skill Categories

Based on the antigravity-awesome-skills taxonomy with additions.

## 1. Architecture

**Focus**: System design, technical decisions, scalable patterns

**Includes**:
- ADR (Architecture Decision Records) generation
- System design workflows
- Scalability patterns
- Microservices design
- API architecture
- Database modeling

**Example Skills**:
- `adr-creator` - Generate architecture decision records
- `system-design` - Design scalable systems
- `api-architect` - Design REST/GraphQL APIs

**Relevance Signals in CLAUDE.md**:
- "architecture", "design patterns", "microservices"
- "scalability", "system design", "ADR"

---

## 2. Business

**Focus**: Growth, strategy, market analysis

**Includes**:
- Pricing strategy
- SEO optimization
- Go-to-market planning
- Competitive analysis
- Business model canvas
- Growth metrics

**Example Skills**:
- `seo-optimizer` - Technical SEO analysis
- `pricing-strategy` - Pricing model design
- `gtm-planner` - Go-to-market planning

**Relevance Signals in CLAUDE.md**:
- "marketing", "SEO", "pricing", "growth"
- "business model", "go-to-market", "metrics"

---

## 3. Data & AI

**Focus**: AI/ML applications, data engineering

**Includes**:
- LLM application development
- RAG (Retrieval Augmented Generation)
- Agent building
- Prompt engineering
- Data pipelines
- Observability for AI

**Example Skills**:
- `rag-builder` - Build RAG applications
- `prompt-engineer` - Optimize prompts
- `agent-designer` - Design AI agents
- `llm-observability` - Monitor LLM apps

**Relevance Signals in CLAUDE.md**:
- "AI", "ML", "LLM", "RAG", "agents"
- "embeddings", "vector", "prompt"

---

## 4. Development

**Focus**: Language mastery, framework patterns

**Includes**:
- Language-specific best practices (Python, TypeScript, etc.)
- Framework patterns (React, FastAPI, etc.)
- Code review workflows
- Refactoring patterns
- Performance optimization

**Example Skills**:
- `python-mastery` - Python best practices
- `typescript-strict` - TypeScript patterns
- `react-patterns` - React component patterns
- `fastapi-expert` - FastAPI development

**Relevance Signals in CLAUDE.md**:
- Programming language names
- Framework names (React, Next.js, FastAPI, etc.)
- "code review", "refactoring"

---

## 5. General

**Focus**: Universal productivity skills

**Includes**:
- Planning and task management
- Documentation writing
- Technical writing
- Communication
- Learning workflows

**Example Skills**:
- `planner` - Task planning
- `doc-writer` - Documentation
- `explainer` - Code explanation
- `summarizer` - Content summarization

**Relevance Signals in CLAUDE.md**:
- "documentation", "planning", "writing"
- Generic development workflows

---

## 6. Infrastructure

**Focus**: DevOps, cloud, deployment

**Includes**:
- CI/CD pipelines
- Cloud infrastructure (AWS, GCP, Azure)
- Kubernetes/Docker
- Terraform/IaC
- Monitoring and alerting

**Example Skills**:
- `terraform-expert` - Infrastructure as Code
- `kubernetes-ops` - K8s operations
- `github-actions` - CI/CD workflows
- `aws-architect` - AWS best practices

**Relevance Signals in CLAUDE.md**:
- "Docker", "Kubernetes", "Terraform"
- "CI/CD", "deployment", "AWS/GCP/Azure"
- "infrastructure", "DevOps"

---

## 7. Security

**Focus**: Application security, compliance

**Includes**:
- Application security (OWASP)
- Penetration testing
- Vulnerability analysis
- Security code review
- Compliance (SOC2, GDPR)

**Example Skills**:
- `security-review` - Security code review
- `owasp-checker` - OWASP compliance
- `pentest-assistant` - Penetration testing
- `compliance-checker` - Regulatory compliance

**Relevance Signals in CLAUDE.md**:
- "security", "OWASP", "vulnerability"
- "compliance", "SOC2", "GDPR"
- "authentication", "authorization"

---

## 8. Testing

**Focus**: Quality assurance, test strategies

**Includes**:
- Test-driven development (TDD)
- Unit/integration/e2e testing
- Test automation
- Performance testing
- Mocking strategies

**Example Skills**:
- `tdd-workflow` - Test-driven development
- `pytest-expert` - Python testing
- `playwright-expert` - E2E testing
- `test-generator` - Generate test cases

**Relevance Signals in CLAUDE.md**:
- "testing", "TDD", "pytest", "jest"
- "e2e", "integration tests", "coverage"

---

## 9. Workflow

**Focus**: Automation, process optimization

**Includes**:
- Git workflows
- Code review automation
- PR management
- Issue triage
- Release management

**Example Skills**:
- `git-workflow` - Git best practices
- `pr-reviewer` - PR review automation
- `release-manager` - Release workflows
- `issue-triager` - Issue management

**Relevance Signals in CLAUDE.md**:
- "git", "PR", "code review"
- "workflow", "automation", "release"

---

## 10. Integrations

**Focus**: Third-party service connections

**Includes**:
- SaaS integrations (Slack, Gmail, etc.)
- Payment processors (Stripe, etc.)
- Database services (Supabase, etc.)
- Cloud services (Vercel, Railway, etc.)

**Example Skills**:
- `stripe-integration` - Stripe payments
- `slack-bot` - Slack automation
- `vercel-deploy` - Vercel deployment
- `supabase-expert` - Supabase development

**Relevance Signals in CLAUDE.md**:
- Service names (Stripe, Slack, etc.)
- "integration", "API", "webhook"

---

## Category Detection Algorithm

When analyzing user's CLAUDE.md:

1. **Extract keywords**: Scan for relevance signals
2. **Count matches**: Tally signals per category
3. **Rank categories**: Order by match count
4. **Identify gaps**: Categories with 0 matches but relevant to tech stack

Example:
```
CLAUDE.md mentions: "FastAPI", "React", "pytest", "Docker"

Results:
- Development: 2 matches (FastAPI, React)
- Testing: 1 match (pytest)
- Infrastructure: 1 match (Docker)
- Security: 0 matches ← GAP (relevant for any web app)
```
