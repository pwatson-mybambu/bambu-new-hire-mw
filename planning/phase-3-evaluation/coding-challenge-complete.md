# Coding Challenge: Microservice Extraction
*MyBambu Middleware Architect Assessment*

## Overview
This coding challenge simulates a real-world architectural task you'll face at MyBambu: extracting a microservice from our Django monolith. You'll work with a simplified version of our codebase that mirrors our actual architecture patterns and challenges.

**Time Allocation**: 3-6 hours total
- Core Challenge: 3 hours (required)
- Extension Challenges: 3 hours (optional, but highly recommended for senior candidates)

**Submission Format**: GitHub repository with clear README and documentation

---

## Background Context

MyBambu currently operates a Django monolith with 52 interconnected apps processing financial transactions for millions of users. Your task is to extract a clean, scalable microservice while maintaining system integrity.

You're provided with a simplified Django project containing three tightly-coupled apps:
- `identity`: User management, authentication, KYC
- `payments`: Transaction processing, card management  
- `notifications`: Email, SMS, and push notifications

---

## Core Challenge (3 Hours Required)

### Task: Extract the Notifications Service

Transform the `notifications` app into an independent microservice that can be deployed and scaled separately from the monolith.

### Provided Code Structure

```python
# Current Monolith Structure (simplified)
bambu_monolith/
├── identity/
│   ├── models.py          # User, Profile, KYCDocument
│   ├── views.py           # Authentication endpoints
│   └── services.py        # Business logic
├── payments/
│   ├── models.py          # Transaction, Card, Account
│   ├── views.py           # Payment endpoints
│   └── tasks.py           # Celery tasks
├── notifications/
│   ├── models.py          # NotificationTemplate, NotificationLog
│   ├── services.py        # EmailService, SMSService, PushService
│   ├── tasks.py           # Async notification tasks
│   └── views.py           # Notification preferences API
└── settings.py            # Shared Django settings
```

### Requirements

#### 1. Service Extraction (40% of score)
Create a new microservice structure:

```python
notification_service/
├── api/
│   ├── v1/
│   │   ├── routes.py      # FastAPI/Flask routes
│   │   ├── schemas.py     # Request/response models
│   │   └── middleware.py  # Auth, logging, etc.
├── core/
│   ├── models.py          # Domain models
│   ├── services.py        # Business logic
│   └── repositories.py   # Data access layer
├── adapters/
│   ├── email.py           # Email provider integration
│   ├── sms.py             # SMS provider integration
│   └── push.py            # Push notification integration
├── database/
│   ├── migrations/        # Database migrations
│   └── connection.py      # DB configuration
├── events/
│   ├── publisher.py       # Event publishing
│   └── consumer.py        # Event consumption
├── tests/
│   └── ...                # Comprehensive tests
├── Dockerfile
├── docker-compose.yml
└── requirements.txt
```

#### 2. API Design (20% of score)
Design RESTful APIs with proper versioning:

```yaml
# Required Endpoints
POST   /api/v1/notifications/send
GET    /api/v1/notifications/{id}
GET    /api/v1/notifications/user/{user_id}
PUT    /api/v1/notifications/{id}/status
GET    /api/v1/templates
POST   /api/v1/templates
DELETE /api/v1/templates/{id}
GET    /api/v1/preferences/user/{user_id}
PUT    /api/v1/preferences/user/{user_id}
```

Include:
- OpenAPI/Swagger documentation
- Request/response validation
- Proper HTTP status codes
- Rate limiting headers
- Pagination for list endpoints

#### 3. Data Migration Strategy (20% of score)
Document your approach for:

```sql
-- Current monolith tables to migrate
CREATE TABLE notifications_notificationtemplate (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    subject VARCHAR(255),
    body TEXT,
    type VARCHAR(20),
    variables JSONB,
    created_at TIMESTAMP,
    updated_at TIMESTAMP
);

CREATE TABLE notifications_notificationlog (
    id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES auth_user(id),
    template_id INTEGER REFERENCES notifications_notificationtemplate(id),
    type VARCHAR(20),
    status VARCHAR(20),
    sent_at TIMESTAMP,
    metadata JSONB
);
```

Provide:
- Zero-downtime migration plan
- Data consistency strategy
- Rollback procedures
- Dual-write period handling

#### 4. Integration Patterns (20% of score)

Implement at least two of these patterns:

**Circuit Breaker** for external services:
```python
class CircuitBreaker:
    def __init__(self, failure_threshold=5, timeout=60):
        self.failure_threshold = failure_threshold
        self.timeout = timeout
        self.failure_count = 0
        self.last_failure_time = None
        self.state = 'closed'  # closed, open, half-open
```

**Retry Logic** with exponential backoff:
```python
@retry(max_attempts=3, backoff_factor=2)
def send_email(recipient, subject, body):
    # Implementation
```

**Event-Driven Communication**:
```python
# Publish events when notifications are sent
{
    "event_type": "notification.sent",
    "user_id": 12345,
    "notification_id": "uuid",
    "channel": "email",
    "timestamp": "2024-01-01T00:00:00Z"
}
```

### Deliverables

1. **Source Code**: Complete microservice implementation
2. **API Documentation**: OpenAPI spec with examples
3. **Migration Plan**: Step-by-step migration document (MIGRATION.md)
4. **Architecture Diagram**: Current vs. proposed architecture
5. **README**: Setup instructions, design decisions, trade-offs

---

## Extension Challenges (3 Hours Optional)

### Extension 1: Performance Optimization (1 hour)

Given this problematic code from the monolith:

```python
# Current inefficient code
def get_user_notifications(user_id):
    notifications = []
    templates = NotificationTemplate.objects.all()
    for template in templates:
        logs = NotificationLog.objects.filter(
            user_id=user_id, 
            template_id=template.id
        )
        for log in logs:
            # N+1 query problem
            user = User.objects.get(id=user_id)
            notifications.append({
                'template_name': template.name,
                'user_email': user.email,
                'sent_at': log.sent_at
            })
    return notifications
```

Requirements:
1. Identify all performance issues
2. Provide optimized solution
3. Include database indexes
4. Add caching strategy
5. Benchmark improvements

### Extension 2: Resilience Patterns (1 hour)

Implement comprehensive resilience:

1. **Health Checks**:
```python
GET /health/live    # Kubernetes liveness
GET /health/ready   # Kubernetes readiness
GET /health/startup # Kubernetes startup probe
```

2. **Graceful Shutdown**:
- Complete in-flight requests
- Stop accepting new requests
- Close database connections
- Flush logs and metrics

3. **Bulkhead Pattern**:
- Isolate critical resources
- Separate thread pools for different operations
- Prevent cascade failures

4. **Observability**:
- Structured logging
- Distributed tracing
- Metrics collection
- Error tracking

### Extension 3: Event Streaming (1 hour)

Design and implement event streaming:

1. **Event Schema**:
```python
@dataclass
class NotificationEvent:
    event_id: str
    event_type: str
    aggregate_id: str
    user_id: int
    payload: dict
    metadata: dict
    timestamp: datetime
```

2. **Kafka/RabbitMQ Integration**:
- Producer implementation
- Consumer with error handling
- Dead letter queue
- Message ordering guarantees

3. **Event Sourcing** (bonus):
- Event store design
- Projection handling
- Snapshot strategy

---

## Evaluation Criteria

### Code Quality (30%)
- Clean, readable code following PEP 8
- Proper error handling
- Comprehensive type hints
- Meaningful variable/function names
- DRY principles

### Architecture (25%)
- Clear separation of concerns
- Proper layering (API, Service, Repository)
- Dependency injection
- Testability
- Scalability considerations

### Testing (20%)
- Unit tests for business logic
- Integration tests for APIs
- Test coverage >80%
- Mock external dependencies
- Performance tests (bonus)

### Documentation (15%)
- Clear README with setup instructions
- API documentation
- Architecture decision records (ADRs)
- Migration runbook
- Code comments where necessary

### DevOps (10%)
- Dockerfile following best practices
- Docker Compose for local development
- Environment configuration
- CI/CD pipeline configuration (bonus)
- Monitoring/logging setup

---

## Starter Code

```python
# notifications/services.py (current monolith)
from django.db import models
from django.contrib.auth.models import User
from celery import shared_task
import requests

class NotificationService:
    def __init__(self):
        self.email_provider = EmailProvider()
        self.sms_provider = SMSProvider()
        
    def send_notification(self, user_id, template_name, context):
        user = User.objects.get(id=user_id)
        template = NotificationTemplate.objects.get(name=template_name)
        
        # Process template with context
        subject = self.render_template(template.subject, context)
        body = self.render_template(template.body, context)
        
        # Send via appropriate channel
        if template.type == 'email':
            self.email_provider.send(user.email, subject, body)
        elif template.type == 'sms':
            self.sms_provider.send(user.phone, body)
            
        # Log notification
        NotificationLog.objects.create(
            user_id=user_id,
            template_id=template.id,
            type=template.type,
            status='sent',
            metadata=context
        )
        
    def render_template(self, template_str, context):
        # Simple template rendering
        for key, value in context.items():
            template_str = template_str.replace(f'{{{key}}}', str(value))
        return template_str

@shared_task
def send_async_notification(user_id, template_name, context):
    service = NotificationService()
    service.send_notification(user_id, template_name, context)
```

---

## Submission Guidelines

### Repository Structure
```
your-name-notifications-service/
├── README.md               # Setup and overview
├── MIGRATION.md           # Detailed migration plan
├── ARCHITECTURE.md        # Architecture decisions
├── notification_service/   # Main service code
├── tests/                 # Test suite
├── docs/                  # Additional documentation
│   ├── api/              # API documentation
│   └── diagrams/         # Architecture diagrams
├── scripts/              # Migration scripts
├── .github/              # CI/CD workflows (bonus)
└── docker/               # Docker configuration
```

### README Requirements
Include:
1. **Setup Instructions**: Step-by-step local setup
2. **Design Decisions**: Key architectural choices
3. **Trade-offs**: What you prioritized and why
4. **Assumptions**: Any assumptions made
5. **Future Improvements**: What you'd do with more time
6. **Time Breakdown**: How you spent your time

### Submission Checklist
- [ ] Core microservice implementation
- [ ] All required APIs implemented
- [ ] Tests passing with >80% coverage
- [ ] Docker setup working
- [ ] Migration plan documented
- [ ] Architecture diagram included
- [ ] README complete
- [ ] Code runs locally without errors
- [ ] API documentation accessible
- [ ] At least one extension attempted (for senior roles)

---

## Tips for Success

1. **Start Simple**: Get a working service first, then refine
2. **Document Decisions**: We value your thinking process
3. **Show Real-World Experience**: Include patterns you've used
4. **Consider Production**: Think about monitoring, logging, deployment
5. **Be Pragmatic**: Perfect is the enemy of good
6. **Communicate Trade-offs**: Explain what you'd do differently with more time

---

## Questions?

If you have questions about the challenge:
1. Document your assumptions in the README
2. Make reasonable decisions and explain them
3. Focus on demonstrating your architectural thinking

Good luck! We're excited to see your approach to this real-world challenge.

---

## Appendix: Reference Implementation Hints

### Database Connection Management
```python
from contextlib import contextmanager
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

@contextmanager
def get_db_session():
    session = SessionLocal()
    try:
        yield session
        session.commit()
    except Exception:
        session.rollback()
        raise
    finally:
        session.close()
```

### API Versioning Strategy
```python
from fastapi import APIRouter, Header

router = APIRouter(prefix="/api/v1")

@router.get("/notifications")
async def get_notifications(
    accept_version: str = Header(default="v1"),
    page: int = 1,
    limit: int = 50
):
    # Version-specific logic
    pass
```

### Event Publishing Pattern
```python
import json
from dataclasses import asdict
from kafka import KafkaProducer

class EventPublisher:
    def __init__(self, bootstrap_servers):
        self.producer = KafkaProducer(
            bootstrap_servers=bootstrap_servers,
            value_serializer=lambda v: json.dumps(v).encode()
        )
    
    def publish(self, topic, event):
        self.producer.send(topic, value=asdict(event))
```