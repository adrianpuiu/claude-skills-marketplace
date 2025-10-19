# Domain-Specific Templates Reference

This reference provides specialized templates and patterns for different types of systems.

## Table of Contents

- [Trading and Financial Systems](#trading-and-financial-systems)
- [Real-time Communication Systems](#real-time-communication-systems)
- [E-commerce Platforms](#e-commerce-platforms)
- [Content Management Systems](#content-management-systems)
- [IoT and Sensor Systems](#iot-and-sensor-systems)
- [Machine Learning Pipelines](#machine-learning-pipelines)
- [Developer Tools and IDEs](#developer-tools-and-ides)
- [SaaS Multi-tenant Platforms](#saas-multi-tenant-platforms)

## Trading and Financial Systems

### Specific Requirements Patterns

```markdown
### Market Data Requirements
- THE system SHALL process market data updates within 10 milliseconds
- THE system SHALL maintain orderbook depth of at least 20 levels
- THE system SHALL handle at least 10,000 price updates per second
- THE system SHALL detect order flow patterns across 6 timeframes simultaneously

### Risk Management Requirements  
- THE system SHALL enforce position size limits before order submission
- THE system SHALL calculate portfolio risk in real-time
- THE system SHALL halt trading when daily loss exceeds configured threshold
- THE system SHALL maintain audit trail of all trading decisions

### Order Execution Requirements
- THE system SHALL submit orders within 50ms of signal generation
- THE system SHALL support market, limit, and stop orders
- THE system SHALL track order status until filled or cancelled
- THE system SHALL handle partial fills correctly
```

### Architecture Components

```markdown
### Market Data Handler
- WebSocket connection management
- Order book reconstruction
- Trade/quote normalization
- Data validation and gap detection

### Strategy Engine
- Pattern recognition
- Signal generation
- Multi-timeframe analysis
- Backtesting framework

### Risk Manager
- Position sizing calculator
- Exposure monitoring
- Drawdown tracking
- Correlation analysis

### Execution Engine
- Order routing
- Smart order routing
- Execution algorithms
- Slippage tracking
```

### Critical Design Considerations

```markdown
## Latency Optimization
- Use memory-mapped files for IPC
- Implement lock-free data structures
- CPU affinity for critical threads
- Kernel bypass networking (if applicable)

## Data Consistency
- Sequence number validation
- Gap detection and recovery
- Timestamp synchronization
- Message deduplication

## Failover Strategy
- Hot-standby system
- State replication
- Automatic failover triggers
- Recovery procedures
```

## Real-time Communication Systems

### Specific Requirements Patterns

```markdown
### Connection Management
- THE system SHALL support 10,000 concurrent WebSocket connections
- THE system SHALL detect disconnections within 30 seconds
- THE system SHALL implement automatic reconnection with exponential backoff
- THE system SHALL maintain connection state across server restarts

### Message Delivery
- THE system SHALL deliver messages within 100ms end-to-end
- THE system SHALL guarantee message ordering per user
- THE system SHALL support message persistence for offline users
- THE system SHALL implement read receipts and delivery confirmations

### Presence and Typing
- THE system SHALL update user presence within 5 seconds
- THE system SHALL broadcast typing indicators in real-time
- THE system SHALL handle presence across multiple devices
```

### Architecture Components

```markdown
### WebSocket Gateway
- Connection pooling
- Load balancing
- Protocol upgrade handling
- Heartbeat management

### Message Broker
- Pub/sub messaging
- Message routing
- Queue management
- Dead letter queues

### Presence Service
- User status tracking
- Last seen timestamps
- Device management
- Presence aggregation

### Notification Service
- Push notification integration
- Email fallback
- Notification preferences
- Delivery tracking
```

## E-commerce Platforms

### Specific Requirements Patterns

```markdown
### Product Catalog
- THE system SHALL support hierarchical category structures
- THE system SHALL handle product variants (size, color, etc.)
- THE system SHALL support bulk product import/export
- THE system SHALL maintain inventory accuracy within 1 minute

### Shopping Cart
- THE system SHALL persist cart data for 30 days
- THE system SHALL update cart totals in real-time
- THE system SHALL reserve inventory during checkout
- THE system SHALL handle currency conversion

### Payment Processing
- THE system SHALL integrate with multiple payment gateways
- THE system SHALL tokenize sensitive payment data
- THE system SHALL support refunds and partial refunds
- THE system SHALL maintain PCI compliance

### Order Management
- THE system SHALL generate unique order numbers
- THE system SHALL track order status changes
- THE system SHALL calculate shipping costs
- THE system SHALL support split shipments
```

### Architecture Components

```markdown
### Product Service
- Catalog management
- Search and filtering
- Variant handling
- Inventory tracking

### Cart Service
- Session management
- Price calculation
- Tax computation
- Promotion engine

### Payment Service
- Gateway abstraction
- Transaction processing
- Fraud detection
- Reconciliation

### Order Service
- Order orchestration
- Fulfillment workflow
- Shipping integration
- Returns processing
```

## Content Management Systems

### Specific Requirements Patterns

```markdown
### Content Creation
- THE system SHALL support WYSIWYG and markdown editors
- THE system SHALL auto-save drafts every 30 seconds
- THE system SHALL maintain revision history
- THE system SHALL support collaborative editing

### Media Management
- THE system SHALL process image uploads with resizing
- THE system SHALL generate responsive image variants
- THE system SHALL support video transcoding
- THE system SHALL implement CDN integration

### Publishing Workflow
- THE system SHALL support draft/review/publish states
- THE system SHALL schedule content publication
- THE system SHALL implement role-based permissions
- THE system SHALL generate SEO-friendly URLs
```

## IoT and Sensor Systems

### Specific Requirements Patterns

```markdown
### Device Management
- THE system SHALL auto-discover devices on network
- THE system SHALL support OTA firmware updates
- THE system SHALL maintain device registry
- THE system SHALL handle 100,000+ devices

### Data Ingestion
- THE system SHALL process 1 million messages per second
- THE system SHALL validate sensor data ranges
- THE system SHALL detect anomalies in real-time
- THE system SHALL batch data for storage efficiency

### Edge Computing
- THE system SHALL support edge processing rules
- THE system SHALL aggregate data at edge
- THE system SHALL implement store-and-forward
- THE system SHALL handle intermittent connectivity
```

## Machine Learning Pipelines

### Specific Requirements Patterns

```markdown
### Data Pipeline
- THE system SHALL ingest data from multiple sources
- THE system SHALL validate data quality metrics
- THE system SHALL perform feature engineering
- THE system SHALL version datasets

### Model Training
- THE system SHALL support distributed training
- THE system SHALL track experiments and metrics
- THE system SHALL implement hyperparameter tuning
- THE system SHALL version trained models

### Model Serving
- THE system SHALL serve predictions with <100ms latency
- THE system SHALL support A/B testing
- THE system SHALL monitor model drift
- THE system SHALL implement fallback models
```

### Architecture Components

```markdown
### Feature Store
- Feature computation pipeline
- Feature versioning
- Online/offline serving
- Feature discovery

### Training Infrastructure
- Distributed computing framework
- GPU scheduling
- Experiment tracking
- Resource optimization

### Model Registry
- Model versioning
- Metadata storage
- Deployment automation
- Performance tracking

### Serving Infrastructure
- Load balancing
- Caching layer
- Batch prediction
- Real-time inference
```

## Developer Tools and IDEs

### Specific Requirements Patterns

```markdown
### Code Editor
- THE system SHALL provide syntax highlighting for 20+ languages
- THE system SHALL implement real-time error detection
- THE system SHALL support multi-cursor editing
- THE system SHALL provide code completion within 100ms

### Project Management
- THE system SHALL handle projects with 100,000+ files
- THE system SHALL index code for instant search
- THE system SHALL support workspace configurations
- THE system SHALL integrate with version control

### Debugging
- THE system SHALL support breakpoint debugging
- THE system SHALL provide variable inspection
- THE system SHALL support remote debugging
- THE system SHALL maintain debug history
```

## SaaS Multi-tenant Platforms

### Specific Requirements Patterns

```markdown
### Tenant Management
- THE system SHALL isolate tenant data completely
- THE system SHALL support custom domains per tenant
- THE system SHALL implement usage metering
- THE system SHALL handle tenant onboarding

### Subscription and Billing
- THE system SHALL support multiple pricing tiers
- THE system SHALL calculate usage-based billing
- THE system SHALL integrate with payment processors
- THE system SHALL handle subscription lifecycle

### Customization
- THE system SHALL support white-labeling
- THE system SHALL allow custom workflows per tenant
- THE system SHALL provide API access per tenant
- THE system SHALL support custom integrations
```

### Architecture Components

```markdown
### Tenant Isolation
- Database per tenant vs shared database
- Schema-based separation
- Row-level security
- Connection pooling strategy

### Billing Engine
- Usage tracking
- Invoice generation
- Payment processing
- Dunning management

### API Gateway
- Rate limiting per tenant
- API key management
- Usage analytics
- Version management
```

## Common Non-Functional Requirements

### Performance
```markdown
- Response time: p95 < 200ms, p99 < 500ms
- Throughput: >1000 requests per second
- Concurrent users: >10,000
- Database queries: <50ms
- Cache hit rate: >90%
```

### Scalability
```markdown
- Horizontal scaling capability
- Auto-scaling based on metrics
- Database sharding strategy
- Stateless service design
- Load balancer configuration
```

### Reliability
```markdown
- Uptime: 99.9% availability
- RTO: <1 hour
- RPO: <5 minutes
- Automated failover
- Data replication strategy
```

### Security
```markdown
- TLS 1.3 for all communications
- OAuth 2.0/JWT authentication
- Role-based access control
- Audit logging
- Encryption at rest
- Input validation
- SQL injection prevention
- XSS protection
- Rate limiting
- DDoS protection
```

### Monitoring
```markdown
- Application metrics (Prometheus)
- Distributed tracing (Jaeger/Zipkin)
- Centralized logging (ELK stack)
- Error tracking (Sentry)
- Uptime monitoring
- Custom dashboards
- Alert configuration
- SLA tracking
```

## Task Breakdown Patterns by Domain

### Trading System Tasks
```markdown
1. Market Data Integration
   - Exchange API setup
   - WebSocket implementation
   - Data normalization
   - Storage optimization

2. Strategy Development
   - Indicator calculation
   - Pattern detection
   - Signal generation
   - Backtesting framework

3. Execution System
   - Order management
   - Position tracking
   - Risk controls
   - Performance analytics
```

### Real-time System Tasks
```markdown
1. Connection Layer
   - WebSocket server
   - Session management
   - Load balancing
   - Failover handling

2. Message Processing
   - Message routing
   - Persistence layer
   - Delivery guarantees
   - Presence tracking

3. Client SDKs
   - JavaScript SDK
   - Mobile SDKs
   - Reconnection logic
   - Offline support
```

### E-commerce Tasks
```markdown
1. Product Management
   - Catalog setup
   - Search implementation
   - Inventory system
   - Media handling

2. Purchase Flow
   - Cart implementation
   - Checkout process
   - Payment integration
   - Order processing

3. Customer Experience
   - User accounts
   - Recommendations
   - Reviews/ratings
   - Customer service
```

## Testing Strategies by Domain

### Financial Systems
- Market data replay testing
- Strategy backtesting
- Risk scenario testing
- Regulatory compliance testing
- Latency benchmarking

### Real-time Systems
- Connection stress testing
- Message ordering verification
- Failover testing
- Network partition testing
- Client compatibility testing

### E-commerce
- Load testing (Black Friday simulation)
- Payment gateway testing
- Inventory accuracy testing
- Cart abandonment testing
- Cross-browser testing

## Deployment Patterns

### High-Frequency Trading
```yaml
# Colocation deployment
- Bare metal servers
- Kernel bypass networking
- CPU isolation
- NUMA optimization
- Dedicated network paths
```

### Global SaaS
```yaml
# Multi-region deployment
- Geographic load balancing
- Regional data residency
- CDN configuration
- Database replication
- Disaster recovery
```

### IoT Platform
```yaml
# Edge + Cloud hybrid
- Edge gateway deployment
- Cloud orchestration
- Message queue setup
- Time-series database
- Analytics pipeline
```
