# Core Software Architectures — Quick Reference

````markdown
# 🏗️ CORE SOFTWARE ARCHITEURES

```text
┌─────────────────────────────────────────────────────────────────────┐
│                    SOFTWARE ARCHITEURE EVOLUTION                   │
└─────────────────────────────────────────────────────────────────────┘

MONOLITH  ───────►  N-TIER / 3-TIER  ───────►  MICROSERVICES
(Simple)             (Layered)                  (Distributed)


=====================================================================
1️⃣ MONOLITHIC ARCHITECTURE
=====================================================================

                ┌──────────────────────────┐
                │      SINGLE APP          │
                │──────────────────────────│
Users ───────►  │ UI + Business + DB Logic │
                │ Single Codebase          │
                │ Single Deployment        │
                └──────────────────────────┘
                             │
                             ▼
                       ┌──────────┐
                       │ DATABASE │
                       └──────────┘


✅ BEST FOR
- Small apps
- Startups / MVPs
- Fast development
- Small teams

✅ STRENGTHS
- Simple architecture
- Easy local testing
- Fast communication (function calls)
- Low network latency
- Easy deployment initially

❌ PROBLEMS
- Hard to scale partially
- Tight coupling
- Large codebase over time
- One bug can impact entire app
- Slow deployments as app grows

📌 KEY IDEA
"Everything packaged together."


=====================================================================
2️⃣ N-TIER / 3-TIER ARCHITECTURE
=====================================================================

        ┌──────────────────────┐
        │   PRESENTATION/UI    │
        └──────────────────────┘
                    │
                    ▼
        ┌──────────────────────┐
        │ BUSINESS LOGIC LAYER │
        └──────────────────────┘
                    │
                    ▼
        ┌──────────────────────┐
        │    DATABASE LAYER    │
        └──────────────────────┘


✅ BEST FOR
- Enterprise applications
- Structured business systems
- Medium-large teams

✅ STRENGTHS
- Better separation of concerns
- Easier maintenance
- Layer-specific responsibilities
- Improved testing
- Reusable business layer

❌ PROBLEMS
- Still can become large
- Entire app often deployed together
- Scaling still limited
- Shared database bottleneck

📌 KEY IDEA
"Separate application by layers."


=====================================================================
3️⃣ MICROSERVICES ARCHITECTURE
=====================================================================

                 ┌──────────────┐
                 │ API GATEWAY  │
                 └──────┬───────┘
                        │
 ┌────────────┬─────────┼──────────┬────────────┐
 ▼            ▼         ▼          ▼            ▼

┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐
│ Auth   │ │ Orders │ │Payment │ │Search  │ │Notify  │
│Service │ │Service │ │Service │ │Service │ │Service │
└────┬───┘ └────┬───┘ └────┬───┘ └────┬───┘ └────┬───┘
     ▼          ▼          ▼          ▼          ▼
   DB-A       DB-B       DB-C       DB-D       DB-E


✅ BEST FOR
- Large-scale platforms
- Cloud-native systems
- Independent teams
- High scalability requirements

✅ STRENGTHS
- Independent deployment
- Granular scaling
- High modularity
- Better fault isolation
- Technology flexibility
- Faster feature delivery

❌ PROBLEMS
- Complex architecture
- Network latency
- Distributed debugging
- DevOps dependency
- Monitoring complexity
- Data consistency challenges

📌 KEY IDEA
"Split system by business domains."


=====================================================================
⚡ QUICK COMPARISON
=====================================================================

┌─────────────────────┬───────────┬───────────┬────────────────┐
│ FACTOR              │ MONOLITH  │ N-TIER    │ MICROSERVICES  │
├─────────────────────┼───────────┼───────────┼────────────────┤
│ Deployment          │ Single    │ Layered   │ Independent    │
│ Scaling             │ Whole App │ Partial   │ Per Service    │
│ Complexity          │ Low       │ Medium    │ High           │
│ Network Latency     │ Lowest    │ Medium    │ Highest        │
│ Fault Isolation     │ Weak      │ Moderate  │ Strong         │
│ Team Independence   │ Low       │ Medium    │ High           │
│ Tech Flexibility    │ Low       │ Medium    │ Very High      │
│ Maintenance         │ Hard Later│ Better    │ Modular        │
│ DevOps Need         │ Low       │ Medium    │ Very High      │
│ Best Company Size   │ Small     │ Medium    │ Large          │
└─────────────────────┴───────────┴───────────┴────────────────┘


=====================================================================
🧠 MEMORY TRICK
=====================================================================

MONOLITH
→ "ONE BIG APPLICATION"

N-TIER
→ "SEPARATE BY LAYERS"

MICROSERVICES
→ "SEPARATE BY BUSINESS DOMAINS"


=====================================================================
🚀 REAL-WORLD EXAMPLES
=====================================================================

MONOLITH
- Small ERP
- Basic E-commerce startup
- Blogging system

N-TIER
- Banking applications
- Enterprise HR systems
- Hospital management systems

MICROSERVICES
- Netflix
- Amazon
- Uber
- Spotify


=====================================================================
🎯 INTERVIEW ONE-LINERS
=====================================================================

MONOLITH
"Simple to start, difficult to scale."

N-TIER
"Improves maintainability using layered separation."

MICROSERVICES
"Enables independently deployable business services."
````

```
```
