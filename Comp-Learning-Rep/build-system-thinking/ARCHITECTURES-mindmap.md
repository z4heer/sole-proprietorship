````markdown
# 🏗️ SOFTWARE ARCHITECTURES — MASTER MINDMAP

```markmap
# Software Architectures

## 1. Monolithic Architecture

### Identity
- Single unified application
- Single codebase
- Single deployment unit
- All modules tightly connected

### Internal Components
- UI Layer
- Business Logic
- Data Access Layer
- Database

### Request Flow
- User Request
  - Controller
    - Service Logic
      - Repository
        - Database

### Characteristics
- Low network latency
- Local function calls
- Centralized deployment
- Shared memory/process

### Advantages
- Simple to develop
- Easy debugging initially
- Fast development for MVP
- Easy local testing
- Simple deployment

### Problems
- Tight coupling
- Hard maintenance
- Full app redeployment required
- Difficult partial scaling
- Large codebase growth
- Single point of failure

### Scalability
- Vertical scaling mostly
- Entire app scaled together

### Team Structure
- Shared ownership
- Less independent teams

### Best Use Cases
- Small applications
- Startup MVPs
- Internal tools
- Proof of concepts

### Examples
- Basic ERP
- Blog systems
- Small e-commerce apps

---

## 2. N-Tier / 3-Tier Architecture

### Identity
- Layered architecture
- Separation by technical concern
- Independent logical layers

### Core Layers

#### Presentation Layer
- UI
- Frontend
- API endpoints

#### Business Layer
- Business rules
- Validation
- Processing logic

#### Data Layer
- Database access
- ORM
- Queries

### Request Flow
- User
  - UI Layer
    - Business Layer
      - Data Layer
        - Database

### Characteristics
- Better modularity
- Layer isolation
- Reusable business logic
- Clear responsibilities

### Advantages
- Easier maintenance
- Better code organization
- Improved testing
- Team specialization possible
- Better scalability than monolith

### Problems
- Shared database bottleneck
- Layer dependency complexity
- Still often deployed together
- Can become large over time

### Scalability
- Partial scaling possible
- Layer-based optimization

### Team Structure
- Frontend team
- Backend team
- Database/admin team

### Best Use Cases
- Enterprise systems
- Banking applications
- Hospital systems
- HR platforms

### Examples
- Java Spring enterprise apps
- .NET enterprise systems

---

## 3. Microservices Architecture

### Identity
- Distributed architecture
- Business-domain driven
- Independent services

### Core Components

#### API Gateway
- Routing
- Authentication
- Rate limiting
- Central entry point

#### Services
- Auth Service
- Order Service
- Payment Service
- Notification Service
- Search Service

#### Databases
- Database per service
- Independent ownership

### Request Flow
- Client
  - API Gateway
    - Target Service
      - Service Database

### Communication
- REST APIs
- gRPC
- Message Queues
- Event Streaming

### Characteristics
- Independent deployment
- Distributed system
- Decentralized ownership
- High modularity

### Advantages
- Granular scaling
- Fault isolation
- Technology flexibility
- Faster deployments
- Independent teams
- Better resilience

### Problems
- Network latency
- Distributed debugging
- Complex monitoring
- DevOps dependency
- Data consistency issues
- Higher operational complexity

### Scalability
- Service-level scaling
- Cloud-native optimization
- Horizontal scaling

### Fault Tolerance
- Circuit breaker pattern
- Retry mechanisms
- Fallback services
- Isolation boundaries

### Technology Flexibility
- Java for core systems
- Python for analytics
- Go for performance
- Node.js for APIs

### Team Structure
- Dedicated service teams
- Autonomous ownership

### Best Use Cases
- Large-scale platforms
- Cloud-native systems
- High-traffic applications

### Examples
- Netflix
- Amazon
- Uber
- Spotify

---

## 4. Architecture Comparison

### Deployment

#### Monolith
- Single deployment

#### N-Tier
- Layered deployment

#### Microservices
- Independent deployments

### Scalability

#### Monolith
- Scale full application

#### N-Tier
- Partial layer scaling

#### Microservices
- Scale individual services

### Network Latency

#### Monolith
- Lowest
- Local calls

#### N-Tier
- Medium

#### Microservices
- Highest
- Network communication

### Separation of Concern

#### Monolith
- Low

#### N-Tier
- Medium

#### Microservices
- Very High

### Fault Tolerance

#### Monolith
- Weak

#### N-Tier
- Moderate

#### Microservices
- Strong

### Technology Choice

#### Monolith
- Usually single stack

#### N-Tier
- Limited flexibility

#### Microservices
- Polyglot architecture

### Complexity

#### Monolith
- Simple initially

#### N-Tier
- Moderate

#### Microservices
- High operational complexity

---

## 5. Evolution Path

### Startup Phase
- Monolith

### Growing Enterprise
- N-Tier

### Large Scale Platform
- Microservices

---

## 6. Quick Memory Tricks

### Monolith
- "ONE BIG APPLICATION"

### N-Tier
- "SEPARATE BY LAYERS"

### Microservices
- "SEPARATE BY BUSINESS DOMAINS"

---

## 7. Interview One-Liners

### Monolith
- Simple to build, difficult to scale

### N-Tier
- Better maintainability using layers

### Microservices
- Independently deployable distributed services

```
````
