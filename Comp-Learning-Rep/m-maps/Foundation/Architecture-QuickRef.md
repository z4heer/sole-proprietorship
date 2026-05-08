# Monolith

## What

* Single deployable application
* UI + Business Logic + DB tightly connected
* One codebase, one runtime

## Why

* Fast initial development
* Easier for small teams
* Simple deployment/startup
* Centralized logic

## How

* User request enters one app
* Internal modules call each other directly
* Shared database for all features
* Entire app redeployed for changes

## Core Components

* UI Layer
* Business Logic
* Shared Database
* Authentication
* Logging/Config

## Real-world Usage

* Small business apps
* ERP systems
* Early-stage startups
* Internal enterprise tools

## Owner

* Full-stack teams
* Small engineering teams
* Central DevOps team

## Consumer

* End users
* Web/mobile clients
* Admin/support teams

# Modular Monolith

## What

* Single application with strong internal module boundaries
* Monolith + clean architecture principles

## Why

* Better maintainability
* Easier scaling of teams
* Reduces code coupling
* Easier future microservices migration

## How

* Features split into modules/domains
* Modules communicate via interfaces/events
* Shared deployment but isolated logic
* Central database with domain separation

## Core Components

* Domain Modules
* API Layer
* Shared Runtime
* Module Contracts
* Shared Database

## Real-world Usage

* Growing SaaS platforms
* Mid-size enterprise apps
* FinTech products
* E-commerce platforms

## Owner

* Domain-based teams
* Platform engineering
* Architecture governance teams

## Consumer

* Customers
* Internal business teams
* External partner APIs

# 3-Tier Architecture

## What

* Application separated into 3 logical layers
* Presentation → Business → Data

## Why

* Better separation of concerns
* Easier maintenance/testing
* Independent scaling
* Enterprise standardization

## How

* UI sends request to application layer
* Business layer processes rules/workflows
* Data layer stores/retrieves data
* Response flows back to user

## Core Components

* Presentation Layer
* Application Layer
* Database Layer
* API/Service Layer
* Network/Load Balancer

## Real-world Usage

* Banking systems
* Enterprise portals
* Hospital systems
* Government platforms

## Owner

* Frontend teams
* Backend teams
* DBA/Data teams
* Infrastructure teams

## Consumer

* Employees
* Customers
* Mobile/web apps
* External systems

# Microservices

## What

* Application split into small independent services
* Each service owns one business capability

## Why

* Independent deployment/scaling
* Faster team autonomy
* Better fault isolation
* Technology flexibility

## How

* Services communicate via APIs/events
* Each service owns its database
* API Gateway routes traffic
* Container/Kubernetes orchestration common

## Core Components

* API Gateway
* Independent Services
* Service Discovery
* Databases per Service
* Messaging/Event Bus
* Monitoring/Tracing

## Real-world Usage

* Netflix
* Amazon
* Uber
* Large-scale SaaS platforms

## Owner

* Autonomous product teams
* DevOps/SRE teams
* Platform engineering

## Consumer

* Web/mobile apps
* External APIs
* Partner systems
* Internal services

# Event-Driven Architecture

## What

* Systems communicate using events/messages
* Producers emit events; consumers react

## Why

* Loose coupling
* Real-time processing
* High scalability
* Async communication

## How

* Event producer publishes message
* Broker routes event
* Consumers process independently
* Multiple consumers can react simultaneously

## Core Components

* Event Producer
* Event Broker (Kafka/RabbitMQ)
* Event Consumer
* Queue/Topics
* Stream Processing
* Dead Letter Queue

## Real-world Usage

* Payment notifications
* Stock trading systems
* IoT platforms
* Order tracking systems

## Owner

* Integration teams
* Platform teams
* Streaming/data engineering teams

## Consumer

* Analytics systems
* Notification services
* Fraud detection
* Downstream applications

# System Design

## What

* Blueprint for building scalable/reliable systems
* Combines architecture + infrastructure + operations

## Why

* Handle scale/performance
* Improve reliability/security
* Reduce failures/cost
* Support business growth

## How

* Define requirements
* Design components/interactions
* Plan scaling/storage/networking
* Add monitoring/security/recovery

## Core Components

* Client Applications
* APIs/Services
* Databases/Cache
* Messaging Systems
* CDN/Load Balancer
* Monitoring/Security

## Real-world Usage

* Social media platforms
* Banking apps
* Cloud platforms
* Streaming systems

## Owner

* Solution architects
* Senior engineers
* SRE/DevOps teams
* Security teams

## Consumer

* Business users
* Developers
* Customers
* Enterprise systems

# System Data Flow

## What

* Movement of data through a system
* Request → Processing → Storage → Response

## Why

* Understand runtime behavior
* Optimize performance
* Improve debugging/security
* Identify bottlenecks

## How

* User sends request
* Gateway routes traffic
* Services process data
* Database/cache accessed
* Response returned/logged

## Core Components

* Client/UI
* API Gateway
* Services
* Cache
* Database
* Queue/Event Bus
* Monitoring/Logs

## Real-world Usage

* Login workflows
* Payment processing
* Video streaming
* E-commerce checkout

## Owner

* Backend engineers
* Architects
* DevOps/SRE teams
* Data engineers

## Consumer

* End users
* Internal systems
* Analytics platforms
* Third-party integrations
