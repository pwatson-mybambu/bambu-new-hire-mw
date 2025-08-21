# Interview Guide Summary
*MyBambu Middleware Architect*

## Quick Reference Guide

### Interview Process Overview
1. **Recruiter Screen** (30 min) - Basic qualification, comp alignment
2. **Technical Phone** (45 min) - Django deep dive, architecture philosophy  
3. **Coding Challenge** (3-6 hours take-home) - Microservice extraction
4. **Technical Deep Dive** (90 min) - Code review, whiteboard, optimization
5. **System Design** (60 min) - Scale to 30M users
6. **Behavioral** (45 min) - Leadership, failures, mentorship
7. **Team Fit** (30 min) - Peer assessment
8. **Executive** (30 min) - Strategic vision

### Key Assessment Areas

#### Technical Must-Haves
- Django ORM optimization (N+1 queries, select_related, prefetch_related)
- Monolith decomposition experience (2+ migrations)
- PostgreSQL performance tuning
- API design and versioning
- Integration patterns (circuit breakers, retries)

#### Leadership Qualities
- Technical mentorship track record
- Stakeholder communication
- Pragmatic decision making
- Mission alignment

### Critical Questions by Round

#### Phone Screen
1. "We have 346 N+1 queries. How would you approach fixing them?"
2. "How do you identify service boundaries in a monolith?"
3. "Describe your approach to zero-downtime migrations"

#### Technical Deep Dive
1. Review actual code - identify issues and propose solutions
2. Design payment service extraction with data separation
3. Optimize transaction list API (15 second load time)

#### System Design
Design architecture for:
- 30M users (10x current)
- $170B transaction volume
- 99.99% uptime
- Multi-region compliance
- Real-time fraud detection

#### Behavioral
1. "Tell me about leading a major architectural transformation"
2. "Describe a technical decision that failed"
3. "How have you developed junior engineers?"
4. "Why is financial inclusion important to you?"

### Evaluation Scoring

| Component | Weight | Min Score |
|-----------|--------|-----------|
| Coding Challenge | 40% | 28/40 |
| Technical Interviews | 35% | 24/35 |
| Behavioral | 15% | 9/15 |
| Team Fit | 10% | 6/10 |
| **Total Required** | **100%** | **70/100** |

### Red Flags
- Only greenfield experience
- Advocates complete rewrites
- Cannot explain failures
- No hands-on coding recently
- Poor communication
- Not mission-aligned

### Green Flags  
- Specific transformation examples
- Pragmatic approach
- Clear technical communication
- Mentorship examples
- Passionate about inclusion
- Django contributions

### Compensation Guidelines
- 90-100 points: $170-175K + $20K signing
- 80-89 points: $160-170K + $15K signing
- 70-79 points: $150-160K + $10K signing

## Full Guide Location
Complete interview guide with all questions and rubrics: `/planning/phase-3-evaluation/interview-guide-complete.md`