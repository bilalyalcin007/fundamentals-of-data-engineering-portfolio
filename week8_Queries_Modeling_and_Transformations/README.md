# Week 8 – Queries, Modeling, and Transformations
**Fundamentals of Data Engineering – Joe Reis & Matt Housley**

---

## Week Objective
The goal of **Week 8** is to understand the **transformation stage** of the data engineering lifecycle. This stage is where ingested data is **modeled, transformed, and prepared** so it can reliably support analytics, machine learning, and business decision-making.

Transformations are not just technical operations. They encode **business logic**, determine **data trust**, influence **performance and cost**, and shape how downstream stakeholders interact with data.

---

## What I Focused On This Week

This week concentrated on how data engineers design and operate transformation systems that are:
- Correct and trustworthy
- Performant at scale
- Cost-aware
- Secure and governed
- Aligned with business needs

The topics below follow the structure and intent of *Chapter 8: Queries, Modeling, and Transformation*.

---

## Queries vs. Transformations

Queries and transformations are closely related, but they serve different purposes.

- **Queries** are typically written for direct consumption by analysts, dashboards, or applications.
- **Transformations** reshape raw or semi-processed data into reusable datasets that can support many queries.

Key insight:
> Queries and transformations exist on a continuum. The distinction becomes especially blurry in streaming systems.

As a data engineer, pushing logic into well-designed transformations reduces:
- Repeated logic in dashboards
- Query complexity for analysts
- Inconsistent business definitions

---

## Data Modeling

Data modeling is where **technical systems meet business logic**.

### Key Learnings
- Data engineers must collaborate with business stakeholders when designing models.
- Transformations must reflect **business definitions**, not just raw source fields.
- Schema design directly affects:
  - Query performance
  - Data usability
  - Long-term maintainability

### Schema Evolution
Real-world systems change constantly. This week emphasized handling:
- Added or removed columns
- Data type changes
- Backward compatibility issues

Poorly managed schema changes can break downstream pipelines, dashboards, and ML workflows.

---

## Views and Materialized Views

### Views
Views provide:
- Abstraction over complex joins
- Simplified access patterns
- Security through column- or row-level filtering

They help analysts work efficiently without needing to understand underlying complexity.

### Materialized Views
Materialized views:
- Precompute expensive joins or aggregations
- Improve query performance
- Trade freshness for speed and cost efficiency

Important takeaway:
> A materialized view is effectively a transformation step managed by the database.

Understanding when to use views versus materialized views is essential for scalable analytics systems.

---

## Federated Queries and Data Virtualization

Federated queries allow analytical systems to query data across:
- Object storage
- Relational databases
- External systems

### Benefits
- Reduced data duplication
- Faster access to distributed datasets
- Unified analytics layer

### Risks
- Increased latency
- Dependency on upstream system performance
- Potential overload of source systems

Data virtualization tools (e.g., Trino/Presto) can act as a **logical access layer**, but they must be used intentionally.

---

## Batch and Distributed Processing

### MapReduce Fundamentals
This week revisited MapReduce to understand:
- Distributed scanning of large datasets
- Shuffle and aggregation mechanics
- Horizontal scalability

Although modern systems have evolved, MapReduce concepts still underpin many distributed engines today.

### Evolution Beyond MapReduce
Modern engines improve performance through:
- In-memory processing
- Reduced disk I/O
- More flexible execution models

Understanding these fundamentals helps explain why certain queries are fast or slow at scale.

---

## Streaming Transformations

Streaming introduces new complexity compared to batch processing.

### Key Concepts
- Micro-batching vs true streaming
- Windowing and triggers
- Latency vs throughput trade-offs

### Streaming DAGs
Streaming DAGs enable:
- Real-time enrichment
- Joins across streams
- Continuous metric computation

The correct streaming approach depends on:
- Business latency requirements
- Event volume and velocity
- Operational complexity

---

## Architecture Considerations

### Data Architecture
Transformations are highly sensitive to architectural decisions.

This week highlighted:
- The importance of choosing the right system for OLAP workloads
- Avoiding architectural mismatches (e.g., using OLTP systems for analytics)
- How ingestion and storage decisions impact transformation performance

Good architecture enables reliable transformations without constant tuning.

---

## Orchestration

Simple time-based scheduling does not scale as pipelines grow.

Key points:
- Dependency-based orchestration is critical for complex pipelines
- Orchestration coordinates transformations across multiple systems
- It enables retries, failure handling, and observability

Orchestration acts as the **control plane** for transformation workflows.

---

## Software Engineering Practices

Transformations are production software and must follow engineering best practices.

### Lessons Learned
- Prefer native database functions over custom UDFs
- Write clean, readable, and maintainable SQL
- Use version control and code reviews
- Avoid throwing more compute at inefficient logic

Well-written transformation code improves:
- Performance
- Reliability
- Long-term maintainability

---

## Security in Transformations

Transformations often combine sensitive datasets, increasing security risk.

This week emphasized:
- Column-, row-, and cell-level access controls
- Avoiding credentials in code or repositories
- Encrypting data in transit and at rest

Security must be enforced at the transformation layer, not only at ingestion.

---

## Data Management and Governance

Transformations create **new datasets** that require governance.

Key practices:
- Clear naming conventions aligned with business definitions
- Ownership and documentation
- Data lineage and traceability

Without governance, transformed data quickly becomes untrusted and unusable.

---

## DataOps and Observability

Reliable transformation systems require observability.

### Data Quality
- Validate inputs and outputs
- Detect schema changes and anomalies
- Ensure correctness before downstream consumption

### System Monitoring
- Query performance
- Resource usage
- Cost optimization

Cloud-based systems require a **FinOps mindset**, balancing performance and cost.

---

## Key Takeaways
- Transformations are where data delivers business value
- Data modeling is as important as infrastructure
- Performance, correctness, cost, and security must be balanced
- Observability and DataOps are essential for reliability
- Strong communication with stakeholders is critical
