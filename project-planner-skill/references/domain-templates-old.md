# Domain-Specific Templates Reference (Augmented)

This reference provides specialized templates and patterns for different classes of systems, with emphasis on performance, resilience, compliance, and modular design.

## Table of Contents

- [Trading and Financial Systems](#trading-and-financial-systems)
- [Real-time Communication Systems](#real-time-communication-systems)
- [E-commerce Platforms](#e-commerce-platforms)
- [Content Management Systems](#content-management-systems)
- [IoT and Sensor Systems](#iot-and-sensor-systems)
- [Machine Learning Pipelines](#machine-learning-pipelines)
- [Developer Tools and IDEs](#developer-tools-and-ides)
- [SaaS Multi-tenant Platforms](#saas-multi-tenant-platforms)
- [Data Lakehouse and Analytics Systems](#data-lakehouse-and-analytics-systems)
- [AI Agent and Orchestration Systems](#ai-agent-and-orchestration-systems)
- [Enterprise Integration Platforms](#enterprise-integration-platforms)
- [Common Non-Functional Requirements](#common-non-functional-requirements)
- [Task Breakdown Patterns by Domain](#task-breakdown-patterns-by-domain)
- [Testing Strategies by Domain](#testing-strategies-by-domain)
- [Deployment Patterns](#deployment-patterns)
- [Cross-Cutting Concerns](#cross-cutting-concerns)

---

## Data Lakehouse and Analytics Systems

### Specific Requirements Patterns
```markdown
### Data Ingestion
- THE system SHALL support batch and streaming ingestion (Kafka, CDC, S3)
- THE system SHALL perform schema evolution tracking
- THE system SHALL apply PII masking on ingestion
- THE system SHALL tag datasets with lineage metadata

### Transformation and Modeling
- THE system SHALL implement ELT with modular SQL or Spark jobs
- THE system SHALL validate data quality thresholds before publishing
- THE system SHALL maintain dimensional and data vault models
- THE system SHALL auto-generate transformation DAGs

### Query and Serving
- THE system SHALL support sub-second queries on 1TB datasets
- THE system SHALL cache hot queries automatically
- THE system SHALL expose a semantic layer for BI tools
- THE system SHALL support row/column-level access policies
```

### Architecture Components
```markdown
### Ingestion Layer
- Connectors (Kafka, JDBC, S3)
- Schema registry
- Data deduplication
- Quality scoring

### Transformation Layer
- Orchestration (Airflow/Dagster)
- Versioned pipelines
- Data validation framework
- Incremental load logic

### Serving Layer
- Lakehouse engine (Delta/Apache Iceberg)
- Query acceleration (Dremio, Trino)
- BI API gateway
- Access policy enforcement
```

---

## AI Agent and Orchestration Systems

### Specific Requirements Patterns
```markdown
### Agent Framework
- THE system SHALL support multiple concurrent agents with tool access
- THE system SHALL enable stateful conversation memory per agent
- THE system SHALL provide structured message passing between agents
- THE system SHALL support reflection, reasoning, and self-correction

### Tool Integration
- THE system SHALL integrate with web search, code generation, and web scraping tools
- THE system SHALL enforce sandboxed tool execution
- THE system SHALL maintain an audit log of tool invocations
- THE system SHALL support role-based tool access (Architect, Reviewer, etc.)

### Orchestration and Governance
- THE system SHALL persist agent graphs using LangGraph or BPMN
- THE system SHALL log all reasoning steps for observability
- THE system SHALL support human-in-the-loop override
- THE system SHALL enable replayable task traces
```

### Architecture Components
```markdown
### Agent Runtime
- LLM interface abstraction
- Context window optimization
- Agent memory management
- Dialogue state persistence

### Tool Executor
- Sandboxed runtime (Python subprocess)
- Secure I/O channels
- Timeout management
- Error containment

### Orchestration Layer
- LangGraph workflow execution
- Event-driven state machine
- Result validation and feedback loop
- Graph persistence and visualization
```

---

## Enterprise Integration Platforms

### Specific Requirements Patterns
```markdown
### Connectivity
- THE system SHALL integrate via REST, gRPC, MQ, and event buses
- THE system SHALL support schema transformation (JSON ↔ XML ↔ CSV)
- THE system SHALL provide API mediation and enrichment
- THE system SHALL handle backpressure and retries

### Workflow Orchestration
- THE system SHALL implement BPMN-based flow orchestration
- THE system SHALL support compensation transactions
- THE system SHALL provide SLA monitoring per flow
- THE system SHALL handle versioned workflows

### Observability and Control
- THE system SHALL expose flow metrics (latency, throughput, error rate)
- THE system SHALL support dynamic throttling
- THE system SHALL maintain end-to-end correlation IDs
- THE system SHALL expose management APIs for flow operations
```

### Architecture Components
```markdown
### Integration Layer
- API Gateway
- Event streaming platform
- Transformation engine
- Adapter registry

### Process Layer
- BPMN runtime (Camunda, Zeebe)
- Orchestration rules
- Retry and compensation engine
- SLA enforcement

### Monitoring Layer
- Centralized flow metrics
- Distributed trace correlation
- Failure recovery console
- Audit event repository
```

---

## Cross-Cutting Concerns

### DevSecOps
```markdown
- Implement CI/CD with automated security scans
- Enforce SBOM (Software Bill of Materials) for all builds
- Enable policy-as-code (OPA, Conftest)
- Integrate secrets management (Vault, SSM)
- Implement GitOps for infrastructure deployment
```

### Data Governance
```markdown
- Maintain centralized metadata catalog (DataHub, Amundsen)
- Apply data classification and retention policies
- Automate lineage tracking
- Enforce PII masking and anonymization
- Support regulatory compliance (GDPR, HIPAA)
```

### Observability Maturity
```markdown
Level 1: Metrics only  
Level 2: Metrics + Centralized Logs  
Level 3: Metrics + Logs + Traces  
Level 4: Business KPIs + SLO Dashboards  
Level 5: Autonomous Remediation (AIOps)
```

### High Availability Blueprint
```markdown
- Active-active regional clusters
- Read replicas for critical databases
- Zero-downtime deployments
- Circuit breaker patterns for dependencies
- Stateful failover validation testing
```

### API Governance
```markdown
- Consistent naming and versioning (v1, v2)
- Schema validation and contract testing
- Rate limit and quota enforcement
- Consumer onboarding workflow
- Deprecation policy automation
```
