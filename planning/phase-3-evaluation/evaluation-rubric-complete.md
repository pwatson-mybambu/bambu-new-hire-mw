# Comprehensive Evaluation Rubric
*MyBambu Middleware Architect - Final Assessment Framework*

## Executive Summary
This rubric provides a quantitative framework for evaluating middleware architect candidates across all assessment phases. It ensures consistent, objective evaluation while identifying candidates who can successfully lead MyBambu's architectural transformation.

**Scoring Philosophy**: We prioritize proven experience with monolith decomposition and Django expertise over theoretical knowledge. Candidates must demonstrate both technical excellence and leadership capability.

---

## Overall Scoring Framework

### Total Score Composition
| Component | Weight | Points | Minimum Required |
|-----------|--------|--------|------------------|
| Coding Challenge | 40% | 40 points | 28 points (70%) |
| Technical Interviews | 35% | 35 points | 24 points (69%) |
| Behavioral/Leadership | 15% | 15 points | 9 points (60%) |
| Team Fit | 10% | 10 points | 6 points (60%) |
| **Total** | **100%** | **100 points** | **70 points** |

### Candidate Classification
- **90-100 points**: Exceptional - Fast track offer, above range compensation
- **80-89 points**: Strong Hire - Standard offer, top of range
- **70-79 points**: Hire - Standard offer, mid-range
- **60-69 points**: Borderline - Additional discussion needed
- **<60 points**: No Hire - Does not meet requirements

---

## Section 1: Coding Challenge Rubric (40 Points)

### Core Challenge Assessment (25 points)

#### 1.1 Service Extraction Quality (10 points)

**Exceptional (9-10 points)**
```python
# Clean separation with dependency injection
class NotificationService:
    def __init__(self, email_client: EmailClient, 
                 sms_client: SMSClient,
                 repository: NotificationRepository,
                 event_bus: EventBus):
        self._email = email_client
        self._sms = sms_client
        self._repo = repository
        self._events = event_bus
```
- Clear domain boundaries
- Dependency injection throughout
- Repository pattern for data access
- Event-driven communication
- Proper layering (API → Service → Repository)

**Strong (7-8 points)**
- Good separation of concerns
- Some dependency injection
- Basic repository pattern
- API and service layers distinct

**Adequate (5-6 points)**
- Service extracted but coupled
- Mixed concerns in places
- Basic structure present

**Weak (0-4 points)**
- Poor separation
- Tight coupling remains
- Monolithic patterns persist

#### 1.2 API Design (5 points)

**Evaluation Criteria:**
- RESTful principles (1 point)
- Proper HTTP status codes (1 point)
- Request/response validation (1 point)
- Versioning strategy (1 point)
- OpenAPI documentation (1 point)

**Example of 5-point API:**
```yaml
openapi: 3.0.0
paths:
  /api/v1/notifications:
    post:
      summary: Send notification
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/NotificationRequest'
      responses:
        '202':
          description: Accepted for processing
        '400':
          description: Invalid request
        '429':
          description: Rate limit exceeded
          headers:
            X-RateLimit-Remaining:
              schema:
                type: integer
```

#### 1.3 Data Migration Strategy (5 points)

**5 Points - Comprehensive Strategy:**
- Zero-downtime migration plan
- Dual-write period handling
- Data consistency verification
- Rollback procedures
- Performance considerations

**3-4 Points - Good Strategy:**
- Basic migration plan
- Some consideration of downtime
- Rollback mentioned

**1-2 Points - Minimal Strategy:**
- Simple data copy approach
- No rollback plan

#### 1.4 Code Quality (5 points)

**Scoring Checklist:**
- [ ] Type hints throughout (1 point)
- [ ] Comprehensive error handling (1 point)
- [ ] Clean, readable code (1 point)
- [ ] SOLID principles followed (1 point)
- [ ] No code smells (1 point)

### Extension Challenges (10 points)

#### 1.5 Performance Optimization (4 points)
- Correctly identifies all N+1 queries (1 point)
- Provides optimized solution (1 point)
- Includes proper indexes (1 point)
- Implements caching strategy (1 point)

#### 1.6 Resilience Patterns (3 points)
- Circuit breaker implementation (1 point)
- Health checks (liveness/readiness) (1 point)
- Graceful shutdown (1 point)

#### 1.7 Event Streaming (3 points)
- Event schema design (1 point)
- Producer/consumer implementation (1 point)
- Error handling/DLQ (1 point)

### Testing & Documentation (5 points)

#### 1.8 Test Coverage (3 points)
- **3 points**: >80% coverage, unit + integration tests
- **2 points**: 60-80% coverage, basic tests
- **1 point**: <60% coverage, minimal tests
- **0 points**: No tests

#### 1.9 Documentation (2 points)
- **2 points**: Comprehensive README, ADRs, clear setup
- **1 point**: Basic README, some documentation
- **0 points**: Minimal documentation

---

## Section 2: Technical Interview Rubric (35 Points)

### 2.1 Phone Screen Technical Questions (5 points)

| Topic | Points | Evaluation Criteria |
|-------|--------|-------------------|
| Django Knowledge | 2 | ORM optimization, migrations, signals |
| Architecture Philosophy | 2 | Service boundaries, patterns, trade-offs |
| Problem-Solving | 1 | Clear thinking, systematic approach |

### 2.2 Technical Deep Dive (15 points)

#### Code Review Exercise (5 points)
**Identifies Issues (2.5 points):**
- No error handling specifics
- No retry logic
- Synchronous blocking call
- Tight coupling
- No idempotency

**Provides Solutions (2.5 points):**
- Dependency injection
- Circuit breaker pattern
- Async processing
- Proper error types
- Transaction handling

#### Architecture Whiteboard (5 points)

**Scoring Criteria:**
- Service boundary definition (1 point)
- Data separation strategy (1 point)
- API contract design (1 point)
- Migration phases (1 point)
- Risk mitigation (1 point)

#### Performance Optimization (5 points)

**Problem Identification (2 points):**
- Spots all N+1 queries
- Identifies missing indexes
- Notes lack of pagination
- Sees caching opportunities

**Solution Quality (3 points):**
```python
# Optimal solution example
def get_user_transactions(request, user_id):
    transactions = Transaction.objects.filter(
        user_id=user_id
    ).select_related(
        'merchant__category', 'card'
    ).only(
        'id', 'amount', 'created_at',
        'merchant__name', 
        'merchant__category__name',
        'card__last_four'
    )[:100]  # Pagination
    
    # Use Redis cache
    cache_key = f"user_transactions:{user_id}"
    cached = cache.get(cache_key)
    if cached:
        return JsonResponse(cached)
    
    # ... rest of implementation
```

### 2.3 System Design (15 points)

#### Design Quality Metrics

**Service Architecture (3 points)**
- Logical boundaries based on business domains
- Appropriate service granularity
- Clear ownership model

**Data Architecture (3 points)**
- Database per service vs shared strategy
- Event sourcing consideration
- Consistency guarantees

**Communication Patterns (3 points)**
- Sync vs async decisions
- API gateway design
- Message bus architecture

**Scalability (3 points)**
- Horizontal scaling approach
- Caching strategy
- Load balancing

**Reliability (3 points)**
- Failure handling
- Monitoring/observability
- Disaster recovery

**Scoring Example:**
```
Exceptional (14-15): Comprehensive design addressing all concerns
Strong (11-13): Good design with minor gaps
Adequate (8-10): Basic design meeting requirements
Weak (<8): Significant gaps or misunderstandings
```

---

## Section 3: Behavioral/Leadership Rubric (15 Points)

### 3.1 Leadership Competencies (8 points)

#### Technical Leadership (3 points)
**Exceptional (3 points):**
- Led 3+ architectural transformations
- Clear examples of technical vision
- Influenced organization-wide decisions

**Strong (2 points):**
- Led 1-2 transformations
- Good technical influence
- Team-level impact

**Adequate (1 point):**
- Some leadership experience
- Participated in transformations

#### Mentorship & Development (3 points)

**Evidence Required:**
- Specific examples of mentoring junior→senior
- Teaching methods used
- Measurable outcomes
- Growth mindset demonstrated

**Scoring:**
- 3 points: Multiple success stories, clear methodology
- 2 points: Some mentoring experience, good examples
- 1 point: Limited mentoring, willing to develop
- 0 points: No mentoring experience or interest

#### Stakeholder Management (2 points)

**Evaluation Areas:**
- Communicating technical concepts to non-technical audience
- Negotiating technical debt paydown
- Building trust with product/business
- Managing competing priorities

### 3.2 Cultural Alignment (4 points)

#### Mission Alignment (2 points)
- **2 points**: Deep understanding and passion for financial inclusion
- **1 point**: Interest in mission, basic understanding
- **0 points**: No interest in mission, purely technical focus

#### Work Style Fit (2 points)
- **2 points**: Collaborative, pragmatic, growth mindset
- **1 point**: Generally good fit with minor concerns
- **0 points**: Poor fit (ego-driven, rigid, non-collaborative)

### 3.3 Communication Skills (3 points)

**Assessment Criteria:**
- Clarity of technical explanations (1 point)
- Listening and responding to questions (1 point)
- Written communication in challenge (1 point)

---

## Section 4: Team Fit Rubric (10 Points)

### 4.1 Peer Assessment (5 points)

**Team Feedback Categories:**
- Technical respect (2 points)
- Collaboration style (1 point)
- Communication fit (1 point)
- Culture add (1 point)

**Scoring by Team:**
- Unanimous positive: 5 points
- Mostly positive: 3-4 points
- Mixed feedback: 2 points
- Concerns raised: 0-1 points

### 4.2 Executive Assessment (5 points)

**Evaluation Areas:**
- Strategic thinking (2 points)
- Business alignment (1 point)
- Growth potential (1 point)
- Executive presence (1 point)

---

## Section 5: Reference Check Validation

### Reference Scoring (Pass/Fail - not included in points)

**Must Validate:**
- [ ] Technical expertise confirmed
- [ ] Leadership examples verified
- [ ] No red flags raised
- [ ] Would rehire = Yes

**Red Flags (Automatic Fail):**
- Misrepresented experience
- Performance issues not disclosed
- Interpersonal problems
- "Would not rehire" feedback

---

## Section 6: Final Evaluation Matrix

### Composite Scoring Sheet

```
Candidate: _____________________  Date: _____________

CODING CHALLENGE (40 points)
├── Service Extraction        [___/10]
├── API Design                [___/5]
├── Migration Strategy        [___/5]
├── Code Quality              [___/5]
├── Extensions                [___/10]
└── Testing & Docs            [___/5]
                             = [___/40]

TECHNICAL INTERVIEWS (35 points)
├── Phone Screen              [___/5]
├── Code Review               [___/5]
├── Architecture              [___/5]
├── Performance               [___/5]
└── System Design             [___/15]
                             = [___/35]

BEHAVIORAL/LEADERSHIP (15 points)
├── Technical Leadership      [___/3]
├── Mentorship                [___/3]
├── Stakeholder Mgmt          [___/2]
├── Mission Alignment         [___/2]
├── Work Style                [___/2]
└── Communication             [___/3]
                             = [___/15]

TEAM FIT (10 points)
├── Peer Assessment           [___/5]
└── Executive Assessment      [___/5]
                             = [___/10]

TOTAL SCORE                   [___/100]

References Verified:          [ ] Yes  [ ] No
Recommendation:               [ ] Hire  [ ] No Hire
Compensation Level:           [ ] Top  [ ] Mid  [ ] Entry
```

### Decision Guidelines

#### Automatic Hire (Fast Track)
- Score ≥ 85 points
- No category below 70%
- Strong references
- Available immediately

#### Standard Hire
- Score 70-84 points
- Meets all minimums
- Good references
- Reasonable start date

#### Discussion Required
- Score 60-69 points
- Exceptional in one area but weak in another
- Great culture fit but technical gaps
- Requires VP approval

#### Automatic Rejection
- Score < 60 points
- Failed reference checks
- Misrepresented experience
- Poor culture fit feedback

---

## Section 7: Offer Determination

### Compensation Calculation

| Total Score | Base Salary | Sign-on Bonus | Equity Target |
|------------|-------------|---------------|---------------|
| 90-100 | $170-175K | $20K | 0.25% |
| 80-89 | $160-170K | $15K | 0.20% |
| 70-79 | $150-160K | $10K | 0.15% |

### Negotiation Parameters
- **Max base**: $175K (requires VP approval above)
- **Max sign-on**: $25K (for competing offers)
- **Max equity**: 0.30% (exceptional candidates only)
- **Flexible**: Remote work, start date, PTO

---

## Section 8: Calibration Guidelines

### Inter-rater Reliability
To ensure consistency across interviewers:

1. **Shadow Interviews**: New interviewers shadow 3 interviews
2. **Calibration Sessions**: Monthly review of scores
3. **Score Variance**: Flag if >15 points difference between interviewers
4. **Documentation**: Require specific examples for scores

### Historical Benchmarks
Based on previous successful hires:

- Average successful hire score: 76 points
- Highest performer hired: 92 points
- Lowest successful hire: 71 points
- Failed hire average: 58 points

### Continuous Improvement
- Track 6-month performance vs. interview score
- Adjust weights based on correlation data
- Update rubric quarterly based on learnings
- Maintain score database for analysis

---

## Appendix A: Quick Reference Scoring

### Phone Screen Quick Score
- Django expertise (0-5): ___
- Problem-solving (0-5): ___
- Communication (0-5): ___
- **Proceed if total ≥ 10**

### Coding Challenge Quick Score
- Works correctly (0-5): ___
- Good architecture (0-5): ___
- Well documented (0-5): ___
- **Proceed if total ≥ 10**

### Culture Fit Quick Score
- Mission alignment (0-5): ___
- Team feedback (0-5): ___
- Growth mindset (0-5): ___
- **Proceed if total ≥ 10**

---

## Appendix B: Example Scoring Scenarios

### Scenario 1: Strong Hire
- Coding Challenge: 34/40 (85%)
- Technical: 28/35 (80%)
- Behavioral: 12/15 (80%)
- Team Fit: 8/10 (80%)
- **Total: 82/100 - Offer at $165K**

### Scenario 2: Borderline Candidate
- Coding Challenge: 25/40 (63%)
- Technical: 26/35 (74%)
- Behavioral: 11/15 (73%)
- Team Fit: 7/10 (70%)
- **Total: 69/100 - Requires discussion**

### Scenario 3: Exceptional Candidate
- Coding Challenge: 38/40 (95%)
- Technical: 33/35 (94%)
- Behavioral: 14/15 (93%)
- Team Fit: 10/10 (100%)
- **Total: 95/100 - Top offer + expedited process**