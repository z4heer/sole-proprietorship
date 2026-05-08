# 🖥️ Servers & Infrastructure Options — N-Tier vs Microservices

````markdown id="p2m8vr"
```markmap
# Server Options for Architectures

## 1. N-Tier Architecture Servers

### Typical Structure

#### Presentation Tier
- Web/UI servers

#### Business Tier
- Application servers

#### Data Tier
- Database servers

---

## 2. Common Server Types in N-Tier

### Web Servers

#### Purpose
- Serve frontend/UI
- Handle HTTP requests

#### Examples
- NGINX
- Apache HTTP Server
- IIS

#### Common Tech
- Angular
- React
- JSP
- ASP.NET

---

### Application Servers

#### Purpose
- Execute business logic
- Handle APIs
- Process requests

#### Java
- Tomcat
- JBoss/WildFly
- WebLogic
- WebSphere

#### .NET
- IIS
- Kestrel

#### Python
- Gunicorn
- uWSGI

#### Node.js
- Express Server
- PM2

---

### Database Servers

#### Relational
- MySQL
- PostgreSQL
- Oracle
- SQL Server

#### NoSQL
- MongoDB
- Cassandra

---

## 3. N-Tier Deployment Models

### Single Server
- UI + Backend + DB together

### Two Server Setup
- App Server
- Database Server

### Three Server Setup
- Web Server
- App Server
- DB Server

### Enterprise Setup
- Multiple load-balanced servers

---

## 4. N-Tier Infrastructure Example

### Banking Application

#### Web Layer
- NGINX
- Angular UI

#### Business Layer
- Spring Boot
- Tomcat

#### Database Layer
- Oracle DB

#### Supporting Systems
- Redis Cache
- RabbitMQ

---

## 5. Microservices Server Options

### Core Idea
- Each service independently deployable

### Infrastructure Styles

#### Virtual Machines
- Traditional deployment

#### Containers
- Docker

#### Container Orchestration
- Kubernetes

#### Serverless
- AWS Lambda
- Azure Functions

---

## 6. Common Microservice Servers

### API Gateway Layer

#### Tools
- Kong
- NGINX
- Spring Cloud Gateway
- AWS API Gateway

---

### Service Containers

#### Container Runtime
- Docker

#### Orchestration
- Kubernetes
- OpenShift
- Docker Swarm

---

### Service Runtime Servers

#### Java
- Embedded Tomcat
- Netty

#### Node.js
- Express
- Fastify

#### Python
- FastAPI
- Gunicorn

#### Go
- Native HTTP server

---

## 7. Supporting Infrastructure

### Service Discovery
- Eureka
- Consul
- Kubernetes DNS

### Messaging
- Kafka
- RabbitMQ
- ActiveMQ

### Monitoring
- Prometheus
- Grafana

### Logging
- ELK Stack
- Loki

### Tracing
- Jaeger
- Zipkin

### Cache
- Redis

---

## 8. Microservices Deployment Example

### E-Commerce Platform

#### Entry Layer
- API Gateway

#### Services
- Auth Service
- Product Service
- Order Service
- Payment Service

#### Deployment
- Docker containers

#### Orchestration
- Kubernetes cluster

#### Databases
- DB per service

---

## 9. Cloud Server Options

### AWS

#### N-Tier
- EC2
- RDS
- Elastic Load Balancer

#### Microservices
- EKS
- ECS
- Lambda
- API Gateway

---

### Azure

#### N-Tier
- Virtual Machines
- Azure SQL

#### Microservices
- AKS
- Functions

---

### Google Cloud

#### N-Tier
- Compute Engine

#### Microservices
- GKE
- Cloud Run

---

## 10. On-Premise Options

### N-Tier
- Physical servers
- VMware VMs

### Microservices
- Kubernetes cluster
- OpenShift platform

---

## 11. Scaling Approach

### N-Tier

#### Horizontal Scaling
- Add more app servers

#### Vertical Scaling
- Increase CPU/RAM

---

### Microservices

#### Granular Scaling
- Scale only busy service

#### Auto Scaling
- Kubernetes HPA
- Cloud auto scaling

---

## 12. Infrastructure Complexity

### N-Tier
- Moderate complexity
- Easier operations

### Microservices
- High infrastructure complexity
- Requires DevOps maturity

---

## 13. DevOps & CI/CD

### N-Tier
- Jenkins
- GitLab CI

### Microservices
- Jenkins
- ArgoCD
- Helm
- GitOps pipelines

---

## 14. Real Industry Mapping

### Small Companies
- Monolith + Tomcat + MySQL

### Mid-Size Enterprises
- N-Tier + Load Balancers

### Large Tech Companies
- Kubernetes + Microservices

---

## 15. Interview Perspective

### N-Tier Focus
- Layer separation
- App servers
- Centralized database

### Microservices Focus
- Containers
- Kubernetes
- API Gateway
- Service discovery
- Distributed systems

---

## 16. Memory Tricks

### N-Tier
- "Few large servers"

### Microservices
- "Many small deployable units"

### Kubernetes
- "Operating system for containers"

```
````
