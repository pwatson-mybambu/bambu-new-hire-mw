# Quick Context Reference
*Key findings and numbers for Phase 2-3 work*

## Company Numbers
- **Target Market**: 20-30M underbanked Latinos
- **Current Users**: 92% Hispanic
- **Remittance Volume**: $170B annually
- **Growth**: 5x HQ expansion, 190 new jobs
- **Founded**: 2019
- **HQ**: West Palm Beach, FL

## Architecture Numbers
- **Django Apps**: 52 active (85 directories total)
- **API Endpoints**: 884 views/viewsets
- **Database Tables**: 200+ models
- **Migrations**: 400+ files
- **Lines of Code**: ~500K+ Python
- **External Integrations**: 22 services
- **Celery Queues**: 14 specialized
- **Documentation Pages**: 851 (51% outdated)

## Performance Issues
- **N+1 Queries**: 346 instances (49:1 ratio)
- **Performance Gains Possible**: 70-90%
- **Test Runtime**: 45+ minutes
- **Deployment Time**: 2 weeks
- **MTTR**: 4 hours
- **Change Failure Rate**: 15%

## Critical Integrations
**Very High Complexity**:
- Galileo (200+ APIs) - Banking
- MoneyGram - Remittances
- Salesforce - CRM

**High Complexity**:
- FIS CodeConnect
- TabaPay
- Uniteller
- Veriff
- Arcus BillPay

**Medium Complexity**:
- Plaid, Twilio, Persona, others

## Natural Microservice Boundaries
1. **Identity Service** - persona/, veriff/, datavisor/
2. **Payment Service** - transactions/, tabapay/, astrapay/
3. **International Transfer Service** - cross_border/, imt/, uniteller/
4. **Communication Service** - twilio_mw/, communication/
5. **Banking Core** - galileo/, account/

## Market Research
- **Base Salary Range**: $150-175K
- **Total Comp**: $180-220K first year
- **Django + Microservices Premium**: 10-15%
- **Assessment Duration**: 3-6 hours
- **Assessment Type**: Take-home preferred

## Required Experience
- **Total Experience**: 8-12 years
- **Django**: 5+ years
- **Microservices**: 3+ years
- **Financial Services**: 2+ years
- **Team Leadership**: 2+ years
- **Monolith Decomposition**: 3+ projects

## Pain Points to Address
1. Single database bottleneck
2. No service boundaries
3. Mixed authentication (Knox + JWT)
4. 7 different integration auth patterns
5. No circuit breakers or retry logic
6. No API gateway
7. Inconsistent error handling
8. Limited monitoring/observability

## Success Metrics for New Architect
**6 Months**:
- Extract 2 microservices
- Reduce incidents by 50%
- Implement API gateway

**12 Months**:
- Extract 4 services total
- Daily deployments
- 99.9% uptime
- 30-minute MTTR

## MyBambu Differentiators
- Mission-driven (helping underserved)
- No immigration status checks
- Real technical challenges
- Significant growth opportunity
- Florida lifestyle
- Remote work options

## Interview Focus Areas
1. Django ORM optimization
2. Celery best practices
3. Database scaling strategies
4. API design patterns
5. Microservices extraction experience
6. Integration abstraction patterns
7. Team leadership and mentoring
8. Financial services knowledge

## Coding Challenge Components
**Required**:
- Microservice extraction from Django
- API design with OpenAPI spec
- Database separation strategy
- Error handling and logging
- Docker configuration
- Unit tests

**Bonus**:
- Performance optimization
- Circuit breaker implementation
- Event-driven design
- Monitoring setup

## Red Flags to Screen For
- No actual monolith decomposition experience
- Theoretical knowledge only
- Can't explain trade-offs
- Overcomplicated solutions
- No financial services understanding
- Poor communication skills
- Resistance to legacy code

## Cultural Fit Indicators
- Mission alignment
- Pragmatic approach
- Mentoring mindset
- Collaborative style
- Comfort with ambiguity
- Spanish language (bonus)

---
*Use this for quick reference while creating Phase 2-3 deliverables*