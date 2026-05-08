# 🌐 API Gateway — Mindmap Style Explanation

````markdown
```markmap
# API Gateway

## 1. What Is API Gateway?

### Definition
- Single entry point for clients
- Front door of microservices system
- Receives all external requests
- Routes request to correct service

### Simple Meaning
- Traffic controller for APIs
- Central manager between client and services

### Main Goal
- Hide internal service complexity
- Simplify communication

---

## 2. Why API Gateway Exists?

### Problem Without Gateway

#### Client Issues
- Client must know all service URLs
- Multiple direct service calls
- Complex frontend logic
- Security handling repeated everywhere

#### System Issues
- No centralized control
- Duplicate authentication logic
- Hard monitoring
- Hard rate limiting

### Solution
- One centralized API layer

---

## 3. High-Level Architecture

### Request Flow

#### Step 1
- Client sends request

#### Step 2
- API Gateway receives request

#### Step 3
- Gateway validates/authenticates

#### Step 4
- Gateway routes request

#### Step 5
- Service processes request

#### Step 6
- Response returned via gateway

---

## 4. Visual Flow

### Without API Gateway

- Client
  - Auth Service
  - Payment Service
  - Order Service
  - Search Service
  - Notification Service

### Problems
- Too many endpoints
- Complex frontend
- Security duplication

---

### With API Gateway

- Client
  - API Gateway
    - Auth Service
    - Payment Service
    - Order Service
    - Search Service
    - Notification Service

### Benefits
- Single endpoint
- Centralized control
- Better security

---

## 5. Core Responsibilities

### Request Routing
- Forward request to correct service

### Authentication
- JWT validation
- OAuth validation
- API keys

### Authorization
- Role checking
- Permission validation

### Rate Limiting
- Prevent abuse
- Limit requests per user

### Load Balancing
- Distribute traffic
- Prevent overload

### Logging & Monitoring
- Request tracking
- Centralized logs

### Caching
- Store repeated responses
- Faster performance

### SSL Termination
- HTTPS handling
- Encryption management

### Response Aggregation
- Combine responses from multiple services

---

## 6. Real Example

### Food Delivery App

#### User Opens App
- Gateway receives request

#### Gateway Calls
- Auth Service
- Restaurant Service
- Order Service
- Payment Service

#### Gateway Combines Response
- Sends single final response to client

---

## 7. Internal Request Example

### Request

- GET /orders/123

### Gateway Actions

#### Authentication
- Verify token

#### Authorization
- Check user access

#### Routing
- Forward to Order Service

#### Logging
- Store request details

#### Response
- Return processed response

---

## 8. Benefits

### Simpler Frontend
- One endpoint

### Better Security
- Centralized authentication

### Easier Monitoring
- Central request tracking

### Reduced Complexity
- Client unaware of internal services

### Better Scalability
- Services evolve independently

### Protocol Translation
- REST ↔ gRPC
- HTTP ↔ WebSocket

---

## 9. Problems / Challenges

### Single Point of Failure
- Gateway failure impacts system

### Added Latency
- Extra network hop

### Complex Gateway Logic
- Can become overloaded

### Infrastructure Cost
- Additional component

### Bottleneck Risk
- High traffic concentration

---

## 10. Common Patterns

### API Composition
- Combine multiple service responses

### Backend For Frontend (BFF)
- Separate gateway per frontend type

#### Mobile Gateway
- Optimized for mobile

#### Web Gateway
- Optimized for browser

---

## 11. Popular API Gateway Tools

### Cloud Based
- AWS API Gateway
- Azure API Management
- Google API Gateway

### Open Source
- Kong
- NGINX
- Traefik
- Spring Cloud Gateway

### Service Mesh Related
- Istio Ingress Gateway

---

## 12. Difference From Load Balancer

### Load Balancer
- Distributes traffic only

### API Gateway
- Smart traffic management
- Authentication
- Routing
- Monitoring
- Aggregation

---

## 13. Best Use Cases

### Microservices Architecture
- Most common usage

### Public APIs
- External developer APIs

### Cloud Native Systems
- Kubernetes environments

### Mobile + Web Platforms
- Centralized API management

---

## 14. Memory Trick

### API Gateway
- "Main Entrance of Microservices"

### Think Like
- Airport security + traffic control

---

## 15. Interview One-Liners

### Simple Definition
- API Gateway is a centralized entry point for managing requests in microservices architecture.

### Main Advantage
- Simplifies client interaction and centralizes cross-cutting concerns.

### Main Risk
- Can become bottleneck or single point of failure if not designed properly.

```
````
