# Databases — RDBMS, NoSQL DB, and Caching

*(Beginner → Senior Engineer → Solution Architect Thinking)*

---

# 1. What is a Database?

## Simple Definition

A database is:

> A system used to store, manage, retrieve, and organize data.

---

# Examples of Data

* users
* orders
* payments
* products
* messages
* logs

---

# Main Database Types

| Type  | Meaning                     |
| ----- | --------------------------- |
| RDBMS | Relational Database         |
| NoSQL | Non-relational Database     |
| Cache | Fast temporary data storage |

---

# A. RDBMS

Relational Database Management System.

Stores data in:

* tables
* rows
* columns

Uses:

* SQL language
* relationships

---

# Example Table

| UserID | Name  | City   |
| ------ | ----- | ------ |
| 1      | Zahir | Pune   |
| 2      | Ali   | Mumbai |

---

# Popular RDBMS

| Database             |
| -------------------- |
| MySQL                |
| PostgreSQL           |
| Oracle Database      |
| Microsoft SQL Server |

---

# B. NoSQL Database

NoSQL means:

> Flexible-schema databases for large-scale distributed systems.

Stores:

* JSON
* key-value
* graph
* documents

---

# Example JSON Document

```json
{
  "name": "Zahir",
  "city": "Pune",
  "skills": ["Java", "Python"]
}
```

---

# Popular NoSQL Databases

| Database  | Type        |
| --------- | ----------- |
| MongoDB   | Document    |
| Cassandra | Wide-column |
| Redis     | Key-value   |
| Neo4j     | Graph       |

---

# C. Cache

Cache means:

> Fast temporary storage used to reduce repeated database access.

Purpose:

* speed improvement
* reduced DB load

---

# Example

Instead of:

```text id="7blp1x"
Reading same product from DB 10 lakh times
```

Store temporarily in cache.

---

# Popular Cache Systems

| Cache     |
| --------- |
| Redis     |
| Memcached |

---

# 2. Why Do We Need Them?

# Without Databases

Problems:

* no data persistence
* no transactions
* no search
* no analytics
* no scalability

---

# Without Cache

Problems:

* slow applications
* overloaded DB
* high latency

---

# Real-World Examples

| System   | Database Usage      |
| -------- | ------------------- |
| Banking  | Transactions        |
| WhatsApp | Messages            |
| Amazon   | Orders/products     |
| Netflix  | User preferences    |
| Uber     | Real-time trip data |

---

# 3. How Do They Work?

# RDBMS Flow

```text id="r1m2tz"
Application
    ↓
SQL Query
    ↓
RDBMS
    ↓
Table Storage
    ↓
Response
```

---

# NoSQL Flow

```text id="s4wdcb"
Application
    ↓
JSON/Key Request
    ↓
NoSQL DB
    ↓
Distributed Storage
    ↓
Response
```

---

# Cache Flow

```text id="g64w2g"
Application
    ↓
Check Cache
    ↓
If Found → Return Fast
    ↓
If Missing → Read DB
    ↓
Store in Cache
```

---

# 4. Actors in Database Systems

| Actor              | Role                   |
| ------------------ | ---------------------- |
| User               | Uses application       |
| Application Server | Sends queries          |
| Database           | Stores persistent data |
| Cache              | Speeds up reads        |
| DBA                | Database management    |
| Monitoring System  | Health tracking        |
| Backup System      | Data recovery          |
| Analytics System   | Reporting              |
| Queue System       | Async processing       |

---

# 5. Real-World Analogy

# Library Analogy

| Database Component | Library Equivalent            |
| ------------------ | ----------------------------- |
| RDBMS              | Organized bookshelf           |
| NoSQL              | Flexible storage room         |
| Cache              | Frequently used books on desk |
| Query              | Librarian request             |
| Index              | Book catalog                  |
| Transaction        | Secure borrowing process      |

---

# Example Flow

```text id="6jlwmc"
User asks for book
      ↓
Desk cache checked
      ↓
If unavailable
      ↓
Search library shelves
      ↓
Return book
```

---

# 6. Process Flow

# Example: Product Search in E-commerce

```text id="y2pp8o"
1. User searches product
2. App checks cache
3. Cache miss occurs
4. DB query executed
5. Product data fetched
6. Data stored in cache
7. Response sent to user
```

---

# Database Internal Flow

```text id="b26z6h"
Query
  ↓
Parser
  ↓
Optimizer
  ↓
Execution Engine
  ↓
Storage Engine
  ↓
Response
```

---

# 7. Metrics Impact

# A. Speed

Measured by:

* query latency
* TPS (transactions/sec)
* IOPS

---

# Cache Impact

```text id="w48ulh"
Cache = milliseconds
DB = slower disk/network operations
```

---

# B. Scaling

## Vertical Scaling

```text id="bov18k"
Increase CPU/RAM/storage
```

## Horizontal Scaling

```text id="7xg9y4"
Add replicas/shards
```

---

# C. Reliability

Methods:

* replication
* backups
* clustering
* failover

---

# D. Safety/Security

Includes:

* encryption
* access control
* RBAC
* audit logs
* masking

---

# E. Cost

Trade-off:

* performance vs infrastructure cost

Examples:

* in-memory cache expensive
* SSD storage costly

---

# F. Failure Handling

Techniques:

* replication
* retries
* backup restore
* WAL logs
* distributed consensus

---

# 8. SDLC Usage

# A. Design Phase

Architect decides:

* SQL or NoSQL?
* cache needed?
* schema design?
* indexing strategy?

---

# B. Development Phase

Developers implement:

* queries
* ORM
* transactions
* caching logic

---

# C. Testing Phase

Includes:

* load testing
* query benchmarking
* failover testing
* deadlock testing

---

# D. Deployment Phase

Using:

* DB clusters
* replication
* containers
* managed cloud DB

---

# E. Monitoring Phase

Metrics:

* CPU
* slow queries
* locks
* cache hit ratio
* replication lag

Tools:

* Grafana
* Prometheus
* pgAdmin
* Mongo Compass

---

# F. Scaling Phase

As data grows:

* sharding
* partitioning
* read replicas
* distributed caching

---

# 9. Senior Engineer Insights

Senior engineers focus on:

| Area               | Thinking              |
| ------------------ | --------------------- |
| Query optimization | Faster execution      |
| Indexing           | Reduce scan time      |
| Transactions       | Data consistency      |
| Connection pooling | Efficient connections |
| Caching strategy   | Reduce DB load        |
| Data modeling      | Efficient storage     |

---

# Senior Engineer Thinking

Instead of:

```text id="0q4dhk"
“Query works”
```

Think:

```text id="dwf8ma"
“How does query behave with 10 crore records?”
```

---

# Important Optimization Areas

* indexing
* normalization
* denormalization
* partitioning
* batching
* async writes

---

# 10. Solution Architect Insights

Architects think about:

| Area              | Focus                       |
| ----------------- | --------------------------- |
| Data consistency  | Business correctness        |
| Scalability       | Future growth               |
| Multi-region DB   | Global systems              |
| Disaster recovery | Data protection             |
| Cost optimization | Infra efficiency            |
| Compliance        | Security/legal requirements |

---

# Architect-Level Questions

* SQL or NoSQL?
* Strong consistency needed?
* Eventual consistency acceptable?
* Multi-master replication?
* Read-heavy or write-heavy?
* Global distribution needed?
* Cache invalidation strategy?

---

# 11. Trade-Offs

# SQL vs NoSQL

| SQL                | NoSQL                    |
| ------------------ | ------------------------ |
| Structured schema  | Flexible schema          |
| ACID               | High scalability         |
| Joins supported    | Faster distributed scale |
| Strong consistency | Eventual consistency     |

---

# Normalization vs Denormalization

| Normalization      | Denormalization |
| ------------------ | --------------- |
| Less redundancy    | Faster reads    |
| Better consistency | More storage    |

---

# Cache Trade-Off

Pros:

* fast response

Cons:

* stale data
* invalidation complexity

---

# Read Replica Trade-Off

Pros:

* scaling reads

Cons:

* replication lag

---

# 12. Common Failures / Problems

# A. Slow Queries

Causes:

* missing indexes
* full table scan
* bad joins

---

# B. Deadlocks

Two transactions wait on each other.

---

# C. Cache Stampede

Many requests hit DB simultaneously after cache expiry.

---

# D. Replication Lag

Replica behind primary DB.

Result:

```text id="2w5zq0"
Stale reads
```

---

# E. Storage Exhaustion

Disk becomes full.

---

# F. Hot Partition Problem

One shard receives too much traffic.

---

# G. Data Corruption

Caused by:

* hardware failure
* software bugs
* bad replication

---

# 13. 60-Second Interview Explanation

> “Databases store and manage application data efficiently. RDBMS systems like MySQL and PostgreSQL use structured schemas, SQL queries, and ACID transactions for consistency. NoSQL databases such as MongoDB and Cassandra provide flexible schemas and distributed scalability for large-scale systems. Caching systems like Redis improve performance by storing frequently accessed data in memory, reducing database load and latency. In system design, database architecture affects scalability, reliability, consistency, cost, and application performance.”

---

# 14. Beginner → Advanced Understanding Flow

# Level 1 — Beginner

Learn:

* tables
* rows
* SQL basics
* CRUD operations

Understand:

```text id="jyj7f7"
How applications store data
```

---

# Level 2 — Intermediate

Learn:

* joins
* indexes
* transactions
* NoSQL basics
* caching

Understand:

```text id="kl3xoz"
How databases scale and optimize
```

---

# Level 3 — Advanced

Learn:

* sharding
* replication
* CAP theorem
* distributed transactions
* consensus algorithms

Understand:

```text id="ls33pw"
Large-scale distributed databases
```

---

# Level 4 — Senior Engineer

Focus:

* performance tuning
* reliability
* query optimization
* cache strategies

---

# Level 5 — Solution Architect

Focus:

* enterprise data architecture
* multi-region systems
* DR strategy
* compliance/security

---

# 15. Summary Using Simple Language

# In Very Simple Terms

Database means:

> Place to store application data.

RDBMS means:

> Organized table-based storage.

NoSQL means:

> Flexible scalable storage.

Cache means:

> Fast temporary memory for repeated data.

---

# Core Flow

```text id="33rbrr"
User Request
    ↓
Application
    ↓
Check Cache
    ↓
If Missing
    ↓
Database Query
    ↓
Store in Cache
    ↓
Return Response
```

---

# Key Goal

Build systems that are:

* fast
* reliable
* scalable
* secure
* cost-efficient

---

# One-Line Memory Formula

```text id="wfy9md"
RDBMS ensures consistency + NoSQL enables scale + Cache improves speed
```

---

# Visual Memory Map

```text id="o6n0sh"
USER
  ↓
APPLICATION
  ↓
CACHE
  ↓
DATABASE
  ↓
REPLICATION/BACKUP
  ↓
MONITORING
  ↓
SCALING
```

---

# Real-World Examples

| System  | Database Focus                 |
| ------- | ------------------------------ |
| Amazon  | massive product/order storage  |
| Netflix | distributed caching            |
| Uber    | real-time NoSQL systems        |
| Google  | distributed databases          |
| Meta    | large-scale cache architecture |
