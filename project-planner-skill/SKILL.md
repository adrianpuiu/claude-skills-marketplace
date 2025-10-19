---
name: project-planner
description: Comprehensive project planning and documentation generator for software projects. Creates structured requirements documents, system design documents, and task breakdown plans with implementation tracking. Use when starting a new project, defining specifications, creating technical designs, or breaking down complex systems into implementable tasks. Supports user story format, acceptance criteria, component design, API specifications, and hierarchical task decomposition with requirement traceability.
---

# Project Planner Skill

This skill provides templates and guidance for generating comprehensive project planning documents that serve as blueprints for AI-assisted implementation.

## Quick Start

When a user wants to start a new project, generate three core documents:
1. **Requirements Document** - User stories with acceptance criteria
2. **Design Document** - Technical architecture and component specifications  
3. **Implementation Plan** - Hierarchical task breakdown with requirement tracing

## Document Generation Workflow

### 1. Initial Project Understanding

Before generating documents, gather key information:

```
Required Information:
- Project name and purpose
- Target users (single-user local, multi-tenant SaaS, etc.)
- Core functionality (3-5 main features)
- Technical preferences (languages, frameworks, deployment)
- Non-functional requirements (performance, security, scalability)
```

### 2. Generate Requirements Document

Use the requirements template to create user-focused specifications:

```python
# Execute this to generate requirements structure
requirements = {
    "introduction": "System purpose and scope",
    "glossary": "Domain-specific terms",
    "requirements": [
        {
            "id": "REQ-X",
            "user_story": "As a [role], I want [feature], so that [benefit]",
            "acceptance_criteria": [
                "WHEN [condition], THE system SHALL [behavior]",
                "WHERE [context], THE system SHALL [behavior]",
                "IF [condition], THEN THE system SHALL [behavior]"
            ]
        }
    ]
}
```

### 3. Generate Design Document

Create technical specifications based on requirements:

```python
# Execute this to generate design structure
design = {
    "overview": "High-level system description",
    "architecture": {
        "diagram": "ASCII or description of layers",
        "components": ["Frontend", "Backend", "Database", "External Services"]
    },
    "components": [
        {
            "name": "Component Name",
            "responsibility": "What it does",
            "key_classes": ["Class descriptions"],
            "interfaces": "API/method signatures",
            "data_flow": "How data moves through",
            "performance": "Targets and constraints"
        }
    ],
    "data_models": "Entity definitions",
    "error_handling": "Strategies for failures",
    "testing_strategy": "Unit, integration, performance",
    "deployment": "Docker, environment, configuration"
}
```

### 4. Generate Implementation Plan

Break down the project into executable tasks:

```python
# Execute this to generate task structure
tasks = {
    "phases": [
        {
            "id": 1,
            "name": "Infrastructure Setup",
            "tasks": [
                {
                    "id": "1.1",
                    "description": "Task description",
                    "subtasks": ["Specific actions"],
                    "requirements_fulfilled": ["REQ-1.1", "REQ-2.3"],
                    "dependencies": [],
                    "estimated_hours": 4
                }
            ]
        }
    ]
}
```

## Requirements Document Template

```markdown
# Requirements Document

## Introduction

[System description in 2-3 sentences. Target user and deployment model.]

## Glossary

- **Term**: Definition specific to this system
- **Component**: Major system module or service
[Add all domain-specific terms]

## Requirements

### Requirement [NUMBER]

**User Story:** As a [user type], I want [capability], so that [benefit]

#### Acceptance Criteria

1. WHEN [trigger/condition], THE [component] SHALL [action/behavior]
2. WHERE [mode/context], THE [component] SHALL [action/behavior]  
3. IF [condition], THEN THE [component] SHALL [action/behavior]
4. THE [component] SHALL [capability with measurable target]

[Repeat for each requirement]
```

### Requirements Best Practices

1. **One capability per requirement** - Each requirement should address a single feature
2. **Testable criteria** - Every criterion must be verifiable
3. **Use SHALL for mandatory** - Consistent RFC 2119 keywords
4. **Include performance targets** - "within X milliseconds/seconds"
5. **Specify all states** - Success, failure, edge cases
6. **Number systematically** - REQ-1, REQ-2 for traceability

### Acceptance Criteria Patterns

```
Behavior criteria:
- WHEN [event occurs], THE system SHALL [respond]
- THE system SHALL [provide capability]
- THE system SHALL [enforce rule/limit]

Conditional criteria:
- IF [condition], THEN THE system SHALL [action]
- WHERE [mode is active], THE system SHALL [behavior]

Performance criteria:
- THE system SHALL [complete action] within [time]
- THE system SHALL support [number] concurrent [operations]
- THE system SHALL maintain [metric] above/below [threshold]

Data criteria:
- THE system SHALL persist [data type] with [attributes]
- THE system SHALL validate [input] against [rules]
- THE system SHALL return [data] in [format]
```

## Design Document Template

```markdown
# Design Document

## Overview

[System architecture summary in 3-4 sentences. Key design decisions and priorities.]

## Architecture

### High-Level Architecture

[ASCII diagram showing major components and data flow]

### Component Interaction Flow

[Sequence or flow description]

## Components and Interfaces

### 1. [Component Name]

**Responsibility:** [Single sentence description]

**Key Classes:**
- `ClassName`: [Purpose and main methods]
- `ServiceName`: [What it manages]

**Interfaces:**
```language
class InterfaceName:
    def method_name(params) -> ReturnType
    # Core methods only
```

**Data Flow:**
- Receives [input] from [source]
- Processes by [algorithm/logic]
- Outputs [result] to [destination]

**Performance:**
- Target: [metric and value]
- Constraints: [limitations]

[Repeat for each major component]

## Data Models

### [Entity Name]
```language
@dataclass
class EntityName:
    field: Type
    field: Optional[Type]
    # Core fields only
```

## Error Handling

### [Error Category]
**Types:** [List of error scenarios]
**Handling:** [Strategy and recovery]

## Testing Strategy

### Unit Tests
- [Component]: Test [aspects]
- Coverage target: 80%

### Integration Tests
- [Flow]: Test [end-to-end scenario]

### Performance Tests
- [Operation]: Target [metric]

## Deployment

### Docker Configuration
```yaml
# Essential service definitions only
```

### Environment Variables
```
CATEGORY_VAR=description
```

## Performance Targets

- [Operation]: <[time]
- [Throughput]: >[rate]
- [Resource]: <[limit]

## Security Considerations

- [Authentication method if applicable]
- [Data protection approach]
- [Access control model]
```

### Design Best Practices

1. **Component responsibilities** - Single, clear purpose per component
2. **Interface first** - Define contracts before implementation
3. **Data flow clarity** - Show how data moves through system
4. **Error categories** - Group related failures with consistent handling
5. **Performance targets** - Specific, measurable goals
6. **Deployment ready** - Include Docker and configuration

## Implementation Plan Template

```markdown
# Implementation Plan

- [x] 1. [Phase Name]
  
  - [x] 1.1 [Task name]
    - [Subtask description]
    - [Subtask description]
    - _Requirements: [REQ-X.Y, REQ-A.B]_
    
  - [ ] 1.2 [Task name]
    - [Subtask description]
    - _Requirements: [REQ-X.Y]_
    - _Dependencies: Task 1.1_

- [ ] 2. [Phase Name]

  - [ ] 2.1 [Task name]
    - [Detailed steps or subtasks]
    - _Requirements: [REQ-X.Y]_
    - _Dependencies: Phase 1_

[Continue for all phases]
```

### Task Planning Best Practices

1. **Hierarchical structure** - Phases > Tasks > Subtasks
2. **Requirement tracing** - Link each task to requirements
3. **Dependency marking** - Identify blockers and prerequisites  
4. **Checkbox format** - [x] for complete, [ ] for pending
5. **Atomic tasks** - Each task independently completable
6. **Progressive implementation** - Infrastructure → Core → Features → Polish

### Common Implementation Phases

```markdown
1. **Infrastructure Setup**
   - Project structure
   - Database schema
   - Docker configuration
   - Core dependencies

2. **Data Layer**
   - Models/entities
   - Database operations
   - Migrations

3. **Business Logic**
   - Core algorithms
   - Service classes
   - Validation rules

4. **API/Interface Layer**
   - REST/GraphQL endpoints
   - WebSocket handlers
   - Authentication

5. **Frontend/UI**
   - Component structure
   - State management
   - API integration
   - Responsive design

6. **Integration**
   - External services
   - Third-party APIs
   - Message queues

7. **Testing**
   - Unit tests
   - Integration tests
   - End-to-end tests

8. **DevOps**
   - CI/CD pipeline
   - Monitoring
   - Logging
   - Deployment scripts

9. **Documentation**
   - API documentation
   - User guides
   - Deployment guide
   - README
```

## Document Patterns by Project Type

### Web Application (Full-Stack)

Requirements focus:
- User authentication and authorization
- CRUD operations for entities
- Real-time updates
- Responsive UI
- API design

Design focus:
- 3-tier architecture (Frontend, Backend, Database)
- REST/GraphQL API design
- State management strategy
- Component hierarchy
- Database schema

Tasks focus:
1. Database and backend setup
2. API implementation
3. Frontend components
4. Integration and testing

### Microservices System

Requirements focus:
- Service boundaries
- Inter-service communication
- Data consistency
- Service discovery
- Fault tolerance

Design focus:
- Service decomposition
- API contracts between services
- Message queue/event bus
- Distributed tracing
- Container orchestration

Tasks focus:
1. Service scaffolding
2. Shared libraries/contracts
3. Individual service implementation
4. Integration layer
5. Orchestration setup

### Data Pipeline/ETL

Requirements focus:
- Data sources and formats
- Transformation rules
- Data quality checks
- Schedule/triggers
- Error handling and retry

Design focus:
- Pipeline stages
- Data flow diagram
- Schema evolution
- Monitoring and alerting
- Storage strategy

Tasks focus:
1. Data source connectors
2. Transformation logic
3. Validation and quality checks
4. Scheduling setup
5. Monitoring implementation

### CLI Tool/Library

Requirements focus:
- Command structure
- Input/output formats
- Configuration options
- Error messages
- Performance requirements

Design focus:
- Command parser architecture
- Plugin system (if applicable)
- Configuration management
- Output formatters
- Testing strategy

Tasks focus:
1. Core command structure
2. Business logic implementation
3. Input/output handlers
4. Configuration system
5. Documentation and examples

## Generating Documents for Specific Domains

### Trading/Financial Systems

Additional requirements:
- Risk management rules
- Order execution logic
- Market data handling
- Compliance requirements
- Audit trail

Additional design:
- High-frequency data handling
- Position tracking
- Risk calculations
- Order routing
- Failover strategies

### Real-time Systems (Chat, Gaming, IoT)

Additional requirements:
- Latency targets
- Connection handling
- State synchronization
- Offline support
- Push notifications

Additional design:
- WebSocket/SSE architecture
- State management
- Caching strategy
- Message queuing
- Horizontal scaling

### Machine Learning Systems

Additional requirements:
- Model training pipeline
- Feature engineering
- Model versioning
- Prediction API
- Monitoring/drift detection

Additional design:
- Training infrastructure
- Feature store
- Model registry
- Serving architecture
- A/B testing framework

## Quality Checklist

Before finalizing documents, verify:

### Requirements Document
- [ ] Every requirement has a clear user story
- [ ] All acceptance criteria are testable
- [ ] Non-functional requirements specified (performance, security)
- [ ] Glossary covers all domain terms
- [ ] Requirements are numbered for tracing

### Design Document
- [ ] Architecture diagram included
- [ ] All components have clear responsibilities
- [ ] Interfaces defined for integration points
- [ ] Error handling strategy documented
- [ ] Performance targets specified
- [ ] Deployment configuration included

### Implementation Plan
- [ ] Tasks grouped into logical phases
- [ ] Dependencies identified between tasks
- [ ] Requirements traced to tasks
- [ ] Tasks are atomic and completable
- [ ] Checkbox format for progress tracking

## Example Usage Patterns

### Starting a New Project

```
User: "I want to build an order flow trading automation system"

Response: "I'll help you create comprehensive planning documents for your trading system. Let me gather some key information:

1. Is this for personal use (single-user) or a multi-user platform?
2. Which markets/exchanges will it connect to?
3. What are the core trading strategies or patterns?
4. Any specific performance requirements (latency, throughput)?

Based on this, I'll generate:
- Requirements document with user stories
- System design with components and data flow
- Implementation plan with phases and tasks"
```

### Expanding Existing Requirements

```
User: "Add real-time monitoring dashboard to the requirements"

Response: "I'll add dashboard requirements to your document:

### Requirement 15
**User Story:** As a trader, I want a real-time dashboard, so that I can monitor system performance and trading activity

#### Acceptance Criteria
1. THE Dashboard SHALL display active positions with current P&L
2. THE Dashboard SHALL update market data within 1 second
3. THE Dashboard SHALL provide filtering by symbol, timeframe, and date range
4. WHEN a trade executes, THE Dashboard SHALL reflect it within 100ms"
```

## Common Pitfalls to Avoid

1. **Over-specifying implementation** - Requirements should define "what" not "how"
2. **Vague acceptance criteria** - Avoid "user-friendly" or "fast" without metrics
3. **Missing error cases** - Include failure scenarios in requirements
4. **Circular dependencies** - Ensure task dependencies form a DAG
5. **Untraceable requirements** - Every requirement should map to tasks
6. **Monolithic components** - Break down large components into focused services
7. **Missing data models** - Define core entities early
8. **Ignoring deployment** - Include Docker/deployment from the start

## Output Format

Generate documents in Markdown format for easy editing and version control. Use:
- Clear hierarchical headings (##, ###, ####)
- Code blocks with language hints
- Bulleted and numbered lists
- Tables for structured data
- Checkboxes for task tracking
- Bold for emphasis on key terms
- Inline code for technical terms

Save documents as:
- `requirements.md` - Requirements document
- `design.md` - Design document
- `tasks.md` - Implementation plan

These documents serve as the foundation for AI-assisted implementation, providing clear specifications that can be referenced throughout development.
