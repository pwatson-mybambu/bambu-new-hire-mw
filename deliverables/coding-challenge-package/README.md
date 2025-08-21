# MyBambu Middleware Architect - Coding Challenge

## Overview
Welcome to the MyBambu Middleware Architect coding challenge! This challenge simulates a real-world task you'll face in this role: extracting a microservice from our Django monolith.

**Time Estimate**: 3-6 hours
- Core Challenge: 3 hours (required)
- Extensions: 3 hours (optional but recommended for senior candidates)

## Challenge Context

MyBambu currently operates a Django monolith with 52 interconnected apps. Your task is to demonstrate your ability to:
1. Extract a clean, well-designed microservice
2. Design robust APIs with proper versioning
3. Plan zero-downtime migrations
4. Implement production-ready patterns

## What's Included

```
coding-challenge-package/
├── README.md                    # This file
├── requirements.md              # Detailed challenge requirements
├── starter-code/               
│   ├── notifications/          # Sample Django app to extract
│   ├── identity/               # Related Django app (dependencies)
│   ├── payments/               # Related Django app (dependencies)
│   └── docker-compose.yml      # Local development setup
├── evaluation-key.md           # How we'll evaluate your submission (for transparency)
└── resources/
    ├── architecture-current.png # Current monolith architecture
    └── architecture-target.png  # Target microservices architecture
```

## Getting Started

1. **Review the requirements**: Read `requirements.md` carefully
2. **Set up the environment**: Use the provided Docker setup
3. **Examine the starter code**: Understand the current implementation
4. **Plan your approach**: Document your strategy before coding
5. **Implement the solution**: Focus on the core challenge first
6. **Document your work**: Explain decisions and trade-offs

## Submission Instructions

1. Fork this repository or create a new one
2. Implement your solution
3. Include comprehensive documentation
4. Ensure all tests pass
5. Submit the GitHub repository link

## Evaluation Criteria

We evaluate submissions on:
- **Architecture** (25%): Clean separation, proper patterns
- **Code Quality** (30%): Readable, maintainable, tested
- **API Design** (20%): RESTful, versioned, documented
- **Migration Strategy** (15%): Zero-downtime approach
- **Documentation** (10%): Clear explanations of decisions

See `evaluation-key.md` for detailed scoring rubric.

## Tips for Success

1. **Start simple**: Get a working solution before optimizing
2. **Document decisions**: We value your thought process
3. **Consider production**: Think about monitoring, logging, deployment
4. **Be pragmatic**: Perfect is the enemy of good
5. **Show your experience**: Use patterns you've successfully applied

## Questions?

If something is unclear:
1. Document your assumptions in the README
2. Make reasonable decisions and explain them
3. Focus on demonstrating your architectural thinking

## Time Management Suggestion

- **Hour 1**: Review requirements, plan approach, set up environment
- **Hour 2**: Implement core service extraction
- **Hour 3**: API design, testing, documentation
- **Hours 4-6** (optional): Extensions, optimizations, polish

Good luck! We're excited to see your approach to this real-world challenge.