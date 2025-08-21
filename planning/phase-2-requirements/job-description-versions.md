# Job Description Versions
*MyBambu Middleware Architect Position*

## A. LinkedIn Version (150 words)

**Senior Middleware Architect - Transform Fintech for 30M Underbanked Users**

MyBambu is revolutionizing financial access for Latino immigrants. We're seeking a Senior Middleware Architect to lead our Django monolith transformation, directly impacting 20-30 million underbanked users managing $170B in annual remittances.

You'll architect the evolution of our 52-app Django platform into scalable microservices, optimize 22 critical integrations (Galileo, Plaid, MoneyGram), and eliminate performance bottlenecks affecting millions of daily transactions. This role requires deep Django expertise, proven monolith decomposition experience, and the ability to maintain 99.9% uptime while transforming architecture.

**Requirements:**
• 8+ years backend development, 5+ Django
• Led 2+ monolith-to-microservices migrations
• PostgreSQL optimization, API design expertise
• Financial services experience preferred

**Location:** West Palm Beach, FL (hybrid) or Remote

Join us in building inclusive financial infrastructure that changes lives. Apply with examples of architectural transformations you've led.

---

## B. Website Version (500 words)

**Senior Middleware Architect - Lead the Transformation of Fintech Infrastructure**

### About MyBambu
MyBambu is on a mission to provide comprehensive financial services to 20-30 million underbanked Latino immigrants in the United States. We facilitate over $170 billion in annual remittances to Latin America while offering banking, money transfers, and financial empowerment tools to communities traditionally excluded from mainstream banking. Our platform serves users regardless of immigration status, making financial inclusion a reality for millions.

### The Opportunity
We're seeking an exceptional Senior Middleware Architect to lead the architectural transformation of our Django-based platform. This is a rare opportunity to have massive technical and social impact, architecting systems that process millions of financial transactions while serving communities that depend on our reliability.

### Your Mission
As our Middleware Architect, you'll inherit a robust but monolithic Django application with 52 interconnected apps, 884 API endpoints, and 22 third-party integrations. Your primary mission is to lead its evolution into a scalable, resilient microservices architecture while maintaining our 99.9% uptime commitment.

### Key Responsibilities
• **Architectural Leadership**: Design and execute the decomposition of our Django monolith into domain-driven microservices, starting with Identity, Payments, and International Transfers services
• **Performance Optimization**: Address 346 identified N+1 queries, implement strategic caching, and optimize our PostgreSQL database handling 400+ migrations
• **Integration Excellence**: Modernize our integration layer managing critical connections to Galileo (banking), MoneyGram (remittances), Plaid (bank connections), and 19 other services
• **Technical Mentorship**: Guide a team of 10+ engineers through architectural changes, establishing best practices and design patterns
• **Infrastructure Evolution**: Implement API gateway patterns, event-driven architecture, and containerization strategies using Docker and Kubernetes

### Technical Challenges You'll Solve
• Transform a 500K+ line Django monolith processing financial transactions
• Optimize Celery task processing across 14 specialized queues
• Design resilient integration patterns for 22 third-party services with varying authentication methods
• Reduce deployment cycles from 2 weeks to 2 days through service isolation
• Implement comprehensive monitoring and observability for distributed systems

### Required Qualifications
• 8-12 years of backend development experience
• 5+ years of Django expertise with deep understanding of Django REST Framework, Celery, and ORM optimization
• Proven track record leading 2+ successful monolith-to-microservices transformations
• Expert-level PostgreSQL skills with experience optimizing complex queries and database architecture
• Strong API design skills (REST, GraphQL, gRPC) with understanding of versioning and backward compatibility
• Experience with containerization (Docker) and orchestration (Kubernetes preferred)
• Financial services domain knowledge, particularly in payments and compliance

### Preferred Qualifications
• Experience with AWS services (EC2, RDS, S3, API Gateway)
• Familiarity with specific integrations: Galileo, Plaid, Twilio, or similar platforms
• Spanish language skills (aligning with our user base)
• Previous fintech or regulated industry experience
• Contributions to open-source Django projects

### What We Offer
• Opportunity to impact millions of underserved users
• Technical leadership role with significant architectural influence
• Hybrid work flexibility (West Palm Beach office or remote)
• Collaborative environment solving complex technical challenges
• Growth trajectory as we expand 5x and add 190 new positions

### Location
West Palm Beach, FL (hybrid 2-3 days/week) or fully remote for exceptional candidates

---

## C. Internal Version (Full Details)

**Senior Middleware Architect - Internal Posting**

### Position Overview
**Title**: Senior Middleware Architect  
**Department**: Engineering - Platform Team  
**Reports to**: VP of Engineering  
**Direct Reports**: 2-3 senior engineers (dotted line to 10+ engineers)  
**Location**: West Palm Beach, FL (hybrid) or Remote  
**Start Date**: ASAP (Q4 2024 ideal)  

### Compensation Package
**Base Salary**: $150,000 - $175,000  
**Total First-Year Compensation**: $180,000 - $220,000  
• Sign-on bonus: $10,000 - $20,000  
• Performance bonus: 15-20% of base  
• Equity: Stock options (0.1% - 0.25% based on experience)  
• Benefits: Comprehensive health, 401k match, unlimited PTO  

### Critical Business Context
• Company expanding 5x, adding 190 employees
• Processing volume growing 300% annually
• Technical debt blocking new feature velocity
• Competition intensifying from both fintechs and traditional banks
• Regulatory scrutiny increasing, requiring better compliance infrastructure

### Specific Pain Points to Address

#### Immediate (Month 1)
• Fix 346 N+1 queries causing 30-second page loads
• Implement Redis caching for 70% performance improvement
• Stabilize Celery queues experiencing daily failures
• Document critical integration failure points

#### Short-term (Months 2-3)
• Design API gateway strategy for 884 endpoints
• Create service boundary definitions for 52 Django apps
• Implement circuit breakers for Galileo integration (single point of failure)
• Establish monitoring and alerting for all critical paths

#### Long-term (Months 4-12)
• Extract Identity service (account, KYC, authentication)
• Extract Payment service (transactions, cards, tabapay)
• Extract International Transfer service (cross_border, imt, moneygram)
• Implement event-driven architecture with Kafka/RabbitMQ
• Achieve independent deployability for extracted services

### Performance Metrics (Year 1 Success Criteria)
• Reduce P1 incidents by 50% (current: 2-3 per week)
• Improve deployment frequency from bi-weekly to daily
• Decrease mean time to recovery from 4 hours to 30 minutes
• Achieve 99.9% uptime (current: 99.5%)
• Enable 3-4 teams to deploy independently
• Reduce new engineer onboarding from 4 weeks to 2 weeks

### Technical Debt Inventory
• 400+ database migrations with no cleanup strategy
• 7 different authentication patterns across integrations
• No disaster recovery plan or database replicas
• 51% of documentation is 2+ years outdated
• Hardcoded secrets in 15+ configuration files
• No API versioning strategy
• Mixed use of Knox tokens and JWT without clear boundaries

### Team Dynamics
• Current team: 25 backend engineers, varying skill levels
• Limited microservices experience on existing team
• Strong Django knowledge but architectural gaps
• Some resistance to change from senior team members
• Need leader who can build consensus and drive change

### Interview Process
1. **Recruiter Screen** (30 min) - Culture fit, salary expectations
2. **Technical Phone Screen** (45 min) - Django fundamentals, architecture philosophy
3. **Take-home Challenge** (3-6 hours) - Microservice extraction exercise
4. **On-site/Virtual Loop** (4 hours):
   - Architecture Deep Dive (90 min)
   - System Design (60 min)
   - Behavioral/Leadership (45 min)
   - Team Fit (45 min with potential colleagues)
5. **Executive Interview** (30 min) - VP/C-level alignment

### Ideal Candidate Indicators
• Has migrated financial services or e-commerce platforms
• Comfortable with incremental transformation vs. big-bang rewrite
• Can articulate trade-offs between different architectural patterns
• Shows empathy for both engineering team and end users
• Demonstrates pragmatism over architectural purism
• Experience with regulated industries (PCI DSS, SOC2)

### Red Flags to Avoid
• Only experience with greenfield projects
• Advocates for complete rewrites
• Cannot explain failures or lessons learned
• Lacks hands-on coding ability
• Poor communication with non-technical stakeholders
• Rigid architectural philosophy

### Selling Points for Candidates
• Mission-driven opportunity serving underbanked communities
• Technical leadership role with significant influence
• Budget approved for architectural improvements
• Executive buy-in for transformation initiative
• Growing company with IPO potential
• Diverse, inclusive team culture
• Flexible work arrangements

### Internal Notes
• Previous architect left due to lack of executive support (now resolved)
• Budget allocated for 2-3 additional senior hires under this role
• AWS credits available for infrastructure improvements
• Board has approved 18-month transformation timeline
• Partnership with Galileo critical - cannot disrupt this integration