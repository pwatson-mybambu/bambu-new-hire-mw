# 🚀 CONTINUATION: MyBambu Middleware Architect Hiring Process

## Current Status: Phase 1 COMPLETE ✅ | Starting Phase 2

### Previous Session Context
- **Session Date**: 2025-08-21
- **Completed**: Full Phase 1 Analysis (6 comprehensive documents)
- **Note**: If you need additional context, the conversation history may be at: `~/.claude/conversations/` (latest .jsonl file)

## Project Overview
You are continuing a 3-phase hiring process to find a middleware architect for MyBambu's Django monolith transformation. The role is critical for scaling their fintech platform serving 20-30M underbanked Latino immigrants.

## File Structure & Completed Work

### Project Root
`/Users/patrickwatson/git/bambu-workspace/submodules/bambu-new-hire-mw/`

### ✅ Phase 1 Completed Documents
Location: `planning/phase-1-analysis/`
1. **company-profile.md** - MyBambu serves Latino immigrants, $170B remittance market, 5x growth
2. **architecture-assessment.md** - 52 Django apps, 884 endpoints, monolith decomposition needed
3. **integration-landscape.md** - 22 third-party integrations mapped, Galileo critical
4. **performance-analysis.md** - 346 N+1 queries, 70-90% improvement possible
5. **market-research.md** - $150-175K salary range, 3-6 hour assessment preferred
6. **documentation-index.md** - 851 wiki pages, 51% outdated, critical gaps identified
7. **phase-1-summary.md** - Synthesis of all findings
8. **phase-1-diagram.mmd** - Visual representation of current state

### 📁 Existing Folder Structure
```
bambu-new-hire-mw/
├── CLAUDE.md                           # Project context (review this!)
├── docs/
│   ├── architecture-diagram.html       # Current architecture visualization
│   ├── architecture-diagram.mmd        # Mermaid source
│   ├── references/
│   │   └── orchestrator-prompt.md      # Original plan (reference only)
│   └── temp-continuation/              # THIS FOLDER
│       ├── CONTINUATION_PROMPT.md      # THIS FILE
│       └── key-context.md              # Quick reference (see below)
├── planning/
│   ├── phase-1-analysis/               # ✅ COMPLETE
│   ├── phase-2-requirements/           # 📝 TODO - Your focus
│   └── phase-3-evaluation/             # 📝 TODO - After Phase 2
├── implementation/
│   └── phase-4-execution/              # Future
└── deliverables/                       # Final outputs go here
```

## 🎯 YOUR IMMEDIATE TASKS - PHASE 2

### Task 1: Create Job Descriptions
**File**: `planning/phase-2-requirements/job-description-versions.md`

Create THREE versions:

#### A. LinkedIn Version (150 words)
- Hook: Mission-driven fintech transformation
- Key tech: Django, microservices, 22 integrations
- Impact: 20-30M underbanked users
- Location: West Palm Beach, FL / Remote

#### B. Website Version (500 words)
Include all from LinkedIn plus:
- Detailed technical challenges (from Phase 1 findings)
- Specific technologies from codebase
- Team structure and growth plans
- MyBambu mission and values

#### C. Internal Version
All above plus:
- Salary: $150-175K base
- Total comp: $180-220K first year
- Specific pain points to address
- Performance metrics expected

### Task 2: Build Skills Matrix
**File**: `planning/phase-2-requirements/skills-evaluation-matrix.md`

Create weighted matrix based on Phase 1 findings:

**Critical Skills (40% weight)**:
- Django expertise (5+ years) - Must know: DRF, Celery, Django ORM optimization
- Monolith decomposition experience - Proven track record
- PostgreSQL optimization - Can fix 346 N+1 queries
- API design patterns - REST, GraphQL, gRPC

**Important Skills (35% weight)**:
- Microservices architecture - Docker, Kubernetes, service mesh
- Financial services domain - Payments, compliance, PCI DSS
- Integration patterns - Circuit breakers, retry logic, webhooks
- Team leadership - Can mentor 10+ engineers

**Nice-to-Have (25% weight)**:
- AWS expertise - EC2, RDS, S3, API Gateway
- Specific integrations - Galileo, Plaid, Twilio experience
- Spanish language skills - For mission alignment
- Startup experience - Comfort with ambiguity

### Task 3: Define Candidate Profile
**File**: `planning/phase-2-requirements/ideal-candidate-profile.md`

Based on architecture assessment:
- 8-12 years total experience
- 3+ monolith-to-microservices transformations
- Financial services background preferred
- Has managed 20+ third-party integrations
- Can work with 400+ migration technical debt

### Task 4: Create Phase 2 Diagram
**File**: `planning/phase-2-requirements/phase-2-diagram.mmd`

Update Phase 1 diagram to show:
- Required skills mapped to architecture problems
- Candidate profile overlaid on technical challenges
- Hiring priorities based on pain points

## 🎯 PHASE 3 TASKS (After Phase 2)

### Task 1: Design Coding Challenge
**File**: `planning/phase-3-evaluation/coding-challenge-complete.md`

**3-Hour Core Challenge**:
1. Extract a microservice from provided Django code
2. Must handle one of: Identity, Payments, or Communications
3. Include: API design, database separation, error handling
4. Provide Docker setup and tests

**Optional 3-Hour Extensions**:
- Performance optimization (fix N+1 queries)
- Add circuit breaker for integration
- Design event-driven communication

### Task 2: Create Interview Guide
**File**: `planning/phase-3-evaluation/interview-guide-complete.md`

Structure:
1. **Phone Screen** (30 min) - Django basics, motivation
2. **Technical Round 1** (60 min) - Architecture deep dive
3. **Technical Round 2** (60 min) - Whiteboard system design
4. **Behavioral** (45 min) - Leadership, MyBambu mission fit
5. **Team Fit** (30 min) - Meet potential colleagues

### Task 3: Develop Evaluation Rubric
**File**: `planning/phase-3-evaluation/evaluation-rubric-complete.md`

Scoring framework:
- Code challenge: 40% weight
- Technical interviews: 35% weight
- Behavioral: 15% weight
- Team fit: 10% weight

## 📚 Key Resources & Paths

### Codebase Locations
- **Middleware**: `/Users/patrickwatson/git/bambu-workspace/submodules/bambu-middleware/`
  - 52 Django apps to review
  - Key apps: account/, galileo/, transactions/, cross_border/
  
- **Documentation**: `/Users/patrickwatson/git/bambu-workspace/docs/atlassian-wiki/`
  - 851 pages available
  - Use index.json for navigation

### Reference Materials
- **Parent CLAUDE.md**: `/Users/patrickwatson/git/bambu-workspace/CLAUDE.md`
- **Project CLAUDE.md**: `/Users/patrickwatson/git/bambu-workspace/submodules/bambu-new-hire-mw/CLAUDE.md`

### Available MCPs
- **Context7**: Use for Django/Python framework documentation
- **Brave Search**: Use for market research and job posting examples
- **Filesystem**: Already configured for project access
- **GitHub**: For reviewing candidate portfolios (Phase 3)

## 🔥 Critical Context from Phase 1

### Technical Debt Requiring Architect
- **Performance**: 346 N+1 queries, 49:1 query ratio
- **Architecture**: 52 apps with no service boundaries
- **Database**: Single PostgreSQL, 400+ migrations
- **Integrations**: 22 services, 7 auth patterns, no abstraction
- **Documentation**: 51% outdated, no ADRs, no API specs

### Business Context
- **Users**: 20-30M target, 92% Hispanic currently
- **Market**: $170B annual remittances to Latin America
- **Growth**: 5x HQ expansion, 190 new jobs planned
- **Competition**: Competing with traditional banks and fintechs

### Why This Role Matters
The middleware architect will lead the transformation from monolith to microservices while maintaining 99.9% uptime for financial transactions. This is a high-impact role affecting millions of underserved users.

## 📋 Final Deliverables Checklist

By end of Phase 3, create in `/deliverables/`:

- [ ] `job-posting-linkedin.md` - Ready to post
- [ ] `job-posting-website.md` - Detailed version
- [ ] `coding-challenge-package/`
  - [ ] `README.md` - Instructions
  - [ ] `starter-code/` - Django subset
  - [ ] `requirements.md` - Clear expectations
  - [ ] `evaluation-key.md` - Internal scoring guide
- [ ] `interview-guide.pdf` - For interview panel
- [ ] `hiring-playbook.md` - Complete process documentation

## 🚦 How to Proceed

1. **Start with Phase 2** - Read all Phase 1 documents first
2. **Create deliverables sequentially** - Don't skip ahead
3. **Use actual codebase** - Reference real issues from middleware
4. **Be specific** - Use numbers and examples from analysis
5. **Focus on mission** - Emphasize MyBambu's social impact

## Success Metrics
- Job posting attracts 50+ qualified candidates
- 80% of screened candidates can complete challenge
- Clear differentiation between junior/senior candidates
- Hired architect succeeds in role for 2+ years

## Notes
- All Phase 1 work is complete and high quality
- Focus on synthesis and creation, not re-analysis
- The new architect will inherit significant technical debt
- Balance idealism with pragmatism in requirements

---

**BEGIN PHASE 2 IMMEDIATELY**
Start by creating the job descriptions, using Phase 1 findings as your foundation.