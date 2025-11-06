# 📘 Week 5 – Data Generation in Source Systems

---

## 🌱 Overview
This week focuses on how **data engineers understand and manage source systems**—the origin of all data pipelines. Source systems generate, store, and expose data through various database technologies, APIs, and streaming mechanisms. A strong grasp of these systems helps engineers design robust, scalable, and reliable data architectures.

---

## ⚙️ Key Concepts

### 🗄️ Relational Databases (RDBMS)
Relational databases store data in **tables, rows, and columns** using a **schema** and enforce **ACID** properties for consistency and reliability.  
- Common systems: **MySQL**, **PostgreSQL**, **Oracle**.  
- Ideal for: transactional workloads (OLTP).  
- Key strengths: joins, normalization, integrity constraints, and SQL-based querying.

### 🧩 Non-Relational Databases (NoSQL)
NoSQL databases trade relational constraints for **flexibility, scalability, and high performance**.  
- **Key-value stores** (e.g., Redis, DynamoDB): lightning-fast lookups.  
- **Document stores** (e.g., MongoDB): JSON-based storage for semi-structured data.  
- **Wide-column stores** (e.g., Cassandra, Bigtable): optimized for very large datasets.  
- **Graph databases** (e.g., Neo4j): analyze relationships using nodes and edges.  
- **Time-series databases** (e.g., InfluxDB, Prometheus): optimized for sensor, metric, and log data.  

Each NoSQL model serves a specific use case—choosing the right one depends on **data access patterns**, **scalability needs**, and **consistency requirements**.

---

### 🌐 APIs and Webhooks
APIs expose data and services from source systems.  
- **REST**: the most common paradigm—stateless, simple, and built on HTTP verbs (`GET`, `POST`, `PUT`, `DELETE`).  
- **GraphQL**: created at Facebook; enables clients to query exactly what they need in a single request.  
- **gRPC**: high-performance, binary protocol ideal for inter-service communication.  
- **Webhooks**: event-driven callbacks that send data to a specified endpoint when events occur (often called *reverse APIs*).

---

### ⚡ Message Queues and Event Streaming Platforms
Event-driven architectures move data between systems in real time.  
- **Message queues** (e.g., Amazon SQS, RabbitMQ) decouple producers and consumers, ensuring reliable delivery and buffering.  
- **Event-streaming platforms** (e.g., Apache Kafka, Amazon Kinesis) process continuous data flows with topics, partitions, and offsets for scalability.  
- Engineers must design for **idempotency**, **fault tolerance**, and **partition key distribution** to prevent hotspots.

---

### 🔄 Data Management and DataOps
Data engineers rarely control source systems directly but must ensure quality and governance across them.  
Key areas:  
- **Data governance** – Who owns the data? How is it managed?  
- **Data quality** – Defining validation, integrity, and monitoring standards.  
- **Schema changes** – Prepare for evolution and communicate with upstream teams.  
- **Master data management** – Maintain consistency across systems.  
- **DataOps** – Bridge between DevOps and data engineering to automate testing, deployment, and monitoring of data workflows.

---

## 🧠 Key Takeaways
- Understand how **different source systems generate data** and their impact on ingestion and transformation.  
- Choose database technologies based on **workload type**, **consistency needs**, and **data shape**.  
- Leverage **APIs and streaming** for real-time data integration.  
- Maintain strong collaboration with upstream teams for **data quality, reliability, and security**.  
- Adopt **DataOps principles** for automation, observability, and continuous improvement.

---

💡 *Next step:* In Week 6, you’ll explore how data is **stored and organized for analytics** once it’s ingested from these source systems.
