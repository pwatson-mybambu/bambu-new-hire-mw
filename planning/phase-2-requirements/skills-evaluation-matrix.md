# Skills Evaluation Matrix
*MyBambu Middleware Architect - Weighted Scoring Framework*

## Overview
This matrix provides a quantitative framework for evaluating candidates based on Phase 1 findings. Each skill area is weighted according to its criticality to MyBambu's architectural transformation needs.

**Total Score**: 100 points possible  
**Minimum Viable Score**: 70 points  
**Exceptional Candidate**: 85+ points  

---

## Critical Skills (40% - 40 points)

### 1. Django Framework Expertise (12 points)
**Why Critical**: Core platform is Django 4.2.9 with 52 apps requiring deep understanding

| Proficiency Level | Points | Indicators |
|------------------|--------|------------|
| Expert (10+ years) | 12 | • Has contributed to Django core<br>• Optimized ORM for million+ record datasets<br>• Built custom middleware and backends |
| Advanced (5-10 years) | 10 | • Deep DRF experience with custom serializers<br>• Complex Celery implementations<br>• Django signals and performance optimization |
| Proficient (3-5 years) | 6 | • Built multiple Django applications<br>• Basic ORM optimization<br>• Standard DRF usage |
| Basic (<3 years) | 2 | • Familiar with Django basics<br>• Limited production experience |

### 2. Monolith Decomposition Experience (10 points)
**Why Critical**: Primary mission is transforming 500K+ line monolith

| Experience Level | Points | Evidence Required |
|-----------------|--------|-------------------|
| Led 3+ transformations | 10 | • Can articulate domain boundaries<br>• Shows incremental migration strategies<br>• Demonstrates failure recovery approaches |
| Led 1-2 transformations | 8 | • Successfully extracted services<br>• Understands data separation challenges<br>• Has migration runbooks |
| Participated in transformation | 5 | • Worked on service extraction<br>• Understands the process<br>• Can identify anti-patterns |
| Theoretical knowledge only | 0 | • No hands-on experience |

### 3. PostgreSQL Optimization (9 points)
**Why Critical**: Must fix 346 N+1 queries, optimize 400+ migrations

| Skill Level | Points | Competencies |
|------------|--------|--------------|
| Database architect level | 9 | • Query plan analysis<br>• Index optimization<br>• Partitioning strategies<br>• Read replica configuration |
| Senior DBA skills | 7 | • Complex query optimization<br>• Performance tuning<br>• Backup/recovery planning |
| Intermediate | 4 | • Basic query optimization<br>• Understanding of indexes<br>• EXPLAIN usage |
| Basic | 1 | • SQL knowledge only |

### 4. API Design & Architecture (9 points)
**Why Critical**: 884 endpoints need governance, versioning, gateway strategy

| Expertise | Points | Requirements |
|-----------|--------|--------------|
| API architect | 9 | • REST, GraphQL, gRPC experience<br>• Versioning strategies<br>• API gateway implementation<br>• OpenAPI/documentation |
| Senior API developer | 7 | • Clean API design<br>• Backward compatibility<br>• Rate limiting, authentication |
| Mid-level | 4 | • RESTful principles<br>• Basic API development |
| Junior | 1 | • Limited API experience |

---

## Important Skills (35% - 35 points)

### 5. Microservices Architecture (10 points)
**Why Important**: Target architecture requires distributed systems expertise

| Level | Points | Indicators |
|-------|--------|------------|
| Architect | 10 | • Service mesh experience<br>• Event-driven patterns<br>• Saga implementation<br>• Distributed tracing |
| Senior practitioner | 8 | • Docker/Kubernetes production<br>• Service discovery<br>• Circuit breakers |
| Practitioner | 5 | • Basic containerization<br>• Understanding of patterns |
| Beginner | 2 | • Theoretical knowledge |

### 6. Financial Services Domain (8 points)
**Why Important**: Payments, compliance, and regulatory requirements

| Experience | Points | Domain Knowledge |
|------------|--------|-----------------|
| 5+ years fintech | 8 | • Payment processing flows<br>• PCI DSS compliance<br>• KYC/AML requirements<br>• Transaction integrity |
| 2-5 years fintech | 6 | • Understanding of compliance<br>• Basic payment flows<br>• Security requirements |
| Related domain | 3 | • E-commerce or banking<br>• Some regulatory exposure |
| No domain experience | 0 | • Would need extensive training |

### 7. Integration Patterns & Resilience (9 points)
**Why Important**: 22 third-party integrations with 7 auth patterns

| Expertise | Points | Skills |
|-----------|--------|--------|
| Integration architect | 9 | • Circuit breaker patterns<br>• Webhook handling<br>• Retry strategies<br>• Multi-auth pattern management |
| Senior integration developer | 7 | • Built multiple integrations<br>• Error handling<br>• Monitoring setup |
| Mid-level | 4 | • Basic integration experience<br>• API consumption |
| Junior | 1 | • Limited integration work |

### 8. Team Leadership & Mentoring (8 points)
**Why Important**: Must guide 10+ engineers through transformation

| Leadership Level | Points | Demonstrated Skills |
|-----------------|--------|-------------------|
| Technical lead 5+ years | 8 | • Led architectural changes<br>• Mentored senior engineers<br>• Stakeholder communication |
| Technical lead 2-5 years | 6 | • Team technical guidance<br>• Code review leadership<br>• Technical documentation |
| Senior IC with influence | 3 | • Peer mentoring<br>• Technical influence |
| Individual contributor only | 0 | • No leadership experience |

---

## Nice-to-Have Skills (25% - 25 points)

### 9. AWS/Cloud Expertise (7 points)
**Why Nice-to-Have**: Current infrastructure on AWS, optimization opportunities

| Level | Points | Experience |
|-------|--------|------------|
| AWS architect certified | 7 | • Multi-region deployment<br>• Cost optimization<br>• Security best practices |
| AWS experienced | 5 | • EC2, RDS, S3 proficiency<br>• CloudFormation/Terraform |
| Cloud familiar | 2 | • Basic cloud concepts<br>• Some AWS usage |
| No cloud experience | 0 | • On-premise only |

### 10. Specific Integration Experience (6 points)
**Why Nice-to-Have**: Accelerates onboarding for critical integrations

| Platforms Known | Points | Value |
|-----------------|--------|-------|
| 3+ relevant platforms | 6 | Galileo, Plaid, Twilio, MoneyGram, Stripe |
| 1-2 relevant platforms | 4 | Any from above list |
| Similar platforms | 2 | Other banking/payment APIs |
| No relevant experience | 0 | Generic integration only |

### 11. Spanish Language Skills (4 points)
**Why Nice-to-Have**: 92% Hispanic user base, team diversity

| Proficiency | Points | Benefit |
|-------------|--------|---------|
| Fluent/Native | 4 | • User empathy<br>• Team communication<br>• Documentation translation |
| Conversational | 2 | • Basic communication<br>• Cultural understanding |
| Basic/None | 0 | • English only |

### 12. Startup/Scale-up Experience (4 points)
**Why Nice-to-Have**: Fast-paced environment, resource constraints

| Experience | Points | Indicators |
|------------|--------|------------|
| Multiple startups | 4 | • Comfort with ambiguity<br>• Pragmatic solutions<br>• Rapid iteration |
| One startup | 2 | • Understands pace<br>• Resource awareness |
| Enterprise only | 0 | • May struggle with pace |

### 13. Open Source Contributions (4 points)
**Why Nice-to-Have**: Demonstrates expertise and community engagement

| Contribution Level | Points | Evidence |
|-------------------|--------|----------|
| Maintainer/Major contributor | 4 | • Project maintenance<br>• Significant features<br>• Community leadership |
| Active contributor | 2 | • Regular PRs<br>• Bug fixes<br>• Documentation |
| User only | 0 | • No contributions |

---

## Scoring Guide

### Score Interpretation

| Total Score | Candidate Rating | Recommendation |
|-------------|-----------------|----------------|
| 85-100 | Exceptional | **Strong Hire** - Fast track through process |
| 70-84 | Strong | **Hire** - Proceed with full interview process |
| 60-69 | Potential | **Maybe** - Consider if strong in critical areas |
| 50-59 | Weak | **Likely No** - Only if exceptional other factors |
| <50 | Unqualified | **No** - Does not meet minimum requirements |

### Critical Thresholds
- **Must score 28+ points** in Critical Skills (70% of category)
- **Must score 20+ points** in Important Skills (57% of category)
- **No single Critical Skill below 50%** of available points

### Evaluation Process

1. **Resume Screen** (5 minutes)
   - Quick score based on stated experience
   - Flag for phone screen if 60+ predicted points

2. **Phone Screen** (45 minutes)
   - Validate claimed expertise in Critical Skills
   - Adjust scores based on responses
   - Proceed if 65+ validated points

3. **Technical Assessment** (3-6 hours)
   - Tests Django, API design, and decomposition skills
   - Can add/subtract up to 10 points from score

4. **On-site Interviews** (4 hours)
   - Deep dive into each skill category
   - Final scoring with panel input
   - Hire decision if 70+ final points

---

## Special Considerations

### Score Adjustments (+/- 5 points)

**Positive Adjustments:**
- Exceptional communication skills (+3)
- Perfect culture fit with mission (+2)
- Available to start immediately (+2)
- Willing to relocate to West Palm Beach (+3)

**Negative Adjustments:**
- Poor communication skills (-5)
- Overqualified/flight risk (-3)
- Demanding excessive compensation (-2)
- Multiple job changes (<2 years each) (-3)

### Override Scenarios

**Proceed Despite Low Score If:**
- Exceptional in monolith decomposition (even if weak elsewhere)
- Deep Galileo platform expertise
- Currently at competitor with relevant experience

**Reject Despite High Score If:**
- Cannot provide references
- Fails background check
- Misrepresented experience
- Poor culture fit after team meeting

---

## Matrix Usage Instructions

### For Recruiters
1. Use LinkedIn/Resume to estimate scores
2. Focus on Critical Skills for initial screening
3. Schedule phone screen if 60+ estimated points

### For Hiring Managers
1. Validate scores during phone screen
2. Adjust based on technical assessment
3. Use matrix for comparative candidate ranking

### For Interview Panel
1. Assign interviewers to specific skill categories
2. Score independently, then calibrate
3. Document evidence for each score

### For Final Decision
1. Require 70+ points for offer
2. Consider score adjustments
3. Compare multiple candidates using same matrix

---

## Appendix: Evidence Collection Template

### For Each Skill Category, Document:

**Skill**: [Category Name]  
**Score Assigned**: [X out of Y points]  
**Evidence**:
- Specific examples provided
- Years of relevant experience
- Technologies mentioned
- Projects described
- Depth of knowledge demonstrated

**Red Flags**:
- Gaps in knowledge
- Inability to provide examples
- Vague or evasive answers

**Green Flags**:
- Specific metrics and outcomes
- Lessons learned from failures
- Thoughtful trade-off discussions
- Passion for the domain