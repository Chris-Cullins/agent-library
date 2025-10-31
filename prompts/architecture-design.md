# Architecture Design Prompt

Design or review the architecture for a system or feature.

## Architecture Design Process

### 1. Understand Requirements
- Functional requirements (what it must do)
- Non-functional requirements (performance, scalability, security)
- Constraints (budget, time, technology, team skills)
- Business goals and priorities
- Current system (if extending existing architecture)

### 2. Define Scope and Boundaries
- What's in scope vs out of scope
- System boundaries and interfaces
- Integration points with other systems
- Data ownership and boundaries

### 3. Identify Key Components
- Major system components and their responsibilities
- Services, modules, or layers
- Databases and data stores
- External dependencies
- Infrastructure components

### 4. Design Data Architecture
- Data models and schemas
- Data flow between components
- Storage solutions (SQL, NoSQL, cache, files)
- Data consistency and integrity
- Backup and recovery strategy

### 5. Define Communication Patterns
- Synchronous vs asynchronous communication
- APIs (REST, GraphQL, gRPC)
- Message queues or event streams
- Request/response patterns
- Error handling and retries

### 6. Address Quality Attributes

#### Performance
- Response time requirements
- Throughput needs
- Caching strategy
- Database optimization
- CDN usage

#### Scalability
- Horizontal vs vertical scaling
- Load balancing
- Stateless design
- Database sharding/replication
- Bottleneck identification

#### Reliability
- Fault tolerance
- Redundancy
- Health checks
- Circuit breakers
- Graceful degradation

#### Security
- Authentication and authorization
- Data encryption (in transit and at rest)
- Input validation
- Security scanning
- Secrets management
- Audit logging

#### Maintainability
- Code organization
- Separation of concerns
- Testing strategy
- Deployment process
- Monitoring and observability

### 7. Consider Trade-offs
- Cost vs performance
- Simplicity vs flexibility
- Time to market vs technical debt
- Build vs buy
- Consistency vs availability (CAP theorem)

### 8. Plan for Evolution
- How will this scale?
- What if requirements change?
- How easy is it to add features?
- Can components be replaced?
- Is there a migration path?

## Architecture Documentation Template

```markdown
# [System/Feature] Architecture

## Overview
[High-level description of the system/feature]

## Goals and Requirements
- [Functional requirement 1]
- [Non-functional requirement 1]

## Architecture Diagram
[Include diagram showing components and interactions]

## Components

### [Component 1 Name]
**Responsibility:** [What this component does]
**Technology:** [What it's built with]
**Interfaces:** [APIs, events it exposes]
**Dependencies:** [What it depends on]

### [Component 2 Name]
...

## Data Architecture
- Data models
- Storage solutions
- Data flow
- Consistency model

## Communication
- APIs and protocols
- Message formats
- Error handling
- Authentication

## Quality Attributes

### Performance
[How performance requirements are met]

### Scalability
[Scaling strategy]

### Security
[Security measures]

### Reliability
[Fault tolerance and recovery]

## Trade-offs and Decisions
- [Decision 1]: [Rationale]
- [Decision 2]: [Rationale]

## Alternatives Considered
- [Alternative 1]: [Why not chosen]
- [Alternative 2]: [Why not chosen]

## Risks and Mitigations
- [Risk 1]: [Mitigation]
- [Risk 2]: [Mitigation]

## Open Questions
- [Question 1]
- [Question 2]

## Next Steps
- [Action item 1]
- [Action item 2]
```

## Review Checklist

- [ ] Requirements clearly understood
- [ ] Components are well-defined with clear responsibilities
- [ ] Data architecture is sound
- [ ] Communication patterns are appropriate
- [ ] Quality attributes are addressed
- [ ] Security is properly considered
- [ ] Scalability path is clear
- [ ] Trade-offs are explicitly documented
- [ ] Risks are identified with mitigations
- [ ] Architecture is documented with diagrams
- [ ] Team can understand and implement it
- [ ] Fits with existing systems/standards
