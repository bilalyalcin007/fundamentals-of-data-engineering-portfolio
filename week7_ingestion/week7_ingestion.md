# Week 7 – Data Ingestion

## 🌱 Overview
Week 7 focuses on **data ingestion**, the first stage of every data engineering pipeline. Ingestion is the process of collecting, importing, and moving data from various source systems into storage or processing environments such as data lakes, data warehouses, or streaming platforms.

This chapter emphasizes:
- Different ingestion methods  
- Trade-offs between batch and real-time ingestion  
- Patterns, tools, and operational responsibilities  
- Data quality, security, compliance, and DataOps considerations  

---

## 🧩 Key Concepts

### 🧱 Types of Data Ingestion
Data ingestion falls under two major categories:

#### **1. Batch Ingestion**
- Data is collected and ingested at scheduled intervals.  
- Suitable for large data volumes and well-defined jobs.  
- Common tools: AWS Glue, Apache Airflow, traditional ETL pipelines.

#### **2. Real-Time / Streaming Ingestion**
- Data is ingested continuously as events occur.  
- Ideal for IoT, logs, clickstreams, mobile apps, and real-time analytics.  
- Common tools: Kafka, Kinesis, Pulsar, Flink.

---

## 📦 Common Ingestion Methods

### 🗂️ 1. Databases & File Export
- Data often originates from OLTP databases.
- Export strategies must consider performance impact.
- Options:
  - Export entire tables.
  - Export using filters (by time, partition).
  - Use **read replicas** to reduce load on production systems.

---

### 🔄 2. Change Data Capture (CDC)
Captures only the changes made in a database.

#### **Continuous CDC**
- Streams every event in real time.
- Uses database logs (e.g., PostgreSQL WAL, MySQL binlog).
- Ideal for real-time pipelines.

#### **Batch CDC**
- Periodic snapshot of changes.
- Lower overhead but higher latency.

#### CDC Considerations
- Not free—consumes CPU, storage, bandwidth.
- Avoid running CDC queries directly on primary transactional databases.
- Asynchronous vs synchronous replication trade-offs.

---

### 🌐 3. APIs
APIs expose data from SaaS or partner systems.

Key points:
- Organizations may have hundreds of external APIs.
- No universal standard for API data formats.
- Engineering overhead: parsing, authentication, schema drift handling.
- Rate limits, pagination, throttling must be managed.

---

### 🔌 4. Managed Data Connectors
Examples: Fivetran, Matillion, Airbyte.

Benefits:
- Automate extraction, transformation, and synchronization.
- Reduce engineering overhead.
- Frameworks exist for:
  - CDC
  - Replication
  - Incremental updates
  - Credential management

---

### 📨 5. Message Queues & Event Streaming Platforms
Used for real-time ingestion.

Tools:
- Kafka
- AWS Kinesis
- Google Pub/Sub

Key distinctions:
- **Messages**: transient, removed once consumed.
- **Streams**: durable logs, replayable, support multiple consumers.

---

### 🗃️ 6. Object Storage-Based Ingestion
Object storage (S3, GCS, Azure Blob) is ideal for:
- Storing raw data at scale  
- Ingesting bulk data  
- Transferring between environments  

Supports:
- Any file type (CSV, Parquet, ORC, JSON)
- Secure data exchange
- Temporary signed URLs for uploads

---

### 🧾 7. File Formats & Practical Issues
Common formats:
- **CSV**: simple but prone to errors (escaping, delimiter, schemas).
- **JSON**: flexible but verbose.
- **Parquet/ORC/Arrow**: efficient, columnar, ideal for analytics.

Challenges:
- Schema evolution  
- Encoding consistency  
- Autodetection weaknesses  

---

### 🛠 8. Shell, SSH, and File Transfer Tools

#### **Shell scripts**
- Used to automate ingestion tasks.
- Can run ETL jobs, schedule pipelines, trigger exports.

#### **SSH**
- Secure protocol used with:
  - Tunnels for secure DB access
  - SCP/SFTP for file transfers

#### **SCP / SFTP**
- Common for transferring files between systems.
- Must ensure strong security controls.

---

### 🔗 9. Webhooks
Reverse API model:
- Provider makes **API calls to your endpoint**.
- Common for real-time event notifications.
- Architecture often includes:
  - Lambda (serverless functions)
  - Streaming platform (Kinesis)
  - Object storage (S3)

---

### 🌐 10. Web Interfaces & Web Scraping

#### **Web Interfaces**
- Manual but still common for some SaaS systems.
- Not scalable; prefer APIs when possible.

#### **Web Scraping**
- Extracts data from HTML pages.
- Issues:
  - Legal ambiguity  
  - Unstable HTML structure  
  - Risk of denial-of-service  
  - Scraper maintenance overhead  

---

### 🚚 11. Transfer Appliances (e.g., AWS Snowball)
Used for very large data migrations:
- 100 TB+ datasets  
- Hybrid-cloud and multicloud transfers  
- Cost-effective alternative to large egress fees  

---

## 👥 Stakeholders in Ingestion

### **Upstream Stakeholders (Data Producers)**
- Software engineers  
- Application developers  
- External data providers  

Challenges:
- Misalignment between DevOps and DataOps  
- Lack of communication on schema changes  
- Unexpected regressions  

### **Downstream Stakeholders (Data Consumers)**
- Analysts  
- Data scientists  
- Executives  
- ML practitioners  

Good communication prevents:
- Broken pipelines  
- Out-of-date dashboards  
- Incorrect business metrics  

---

## 🔐 Security, Compliance & Ethics

### Data Security
- Move data securely using encryption in transit.
- Use VPC endpoints, VPNs, private networking.

### Data Management
- Handle schema evolution carefully.
- Track lineage and catalogs from ingestion onward.

### Data Ethics & Privacy
- Only collect data that is necessary.  
- Prefer tokenization over full encryption when possible.  
- Avoid exposing sensitive fields in staging environments.  

---

## 🔧 Orchestration
As pipelines grow:
- Cron jobs are insufficient.
- Use orchestrators like:
  - Airflow  
  - AWS Step Functions  
  - Dagster  
  - Prefect  

Orchestration ensures:
- Scheduling
- Dependencies
- Workflow retries
- Monitoring

---

## 🧠 DataOps & Monitoring
Monitoring is essential for ingestion because failures disrupt downstream processes.

Track:
- Latency  
- Throughput  
- Event volume  
- Error rates  
- SLA adherence  

Build alerts for:
- Job failures  
- Upstream outages  
- Schema drift  

---

## 🧾 Key Takeaways
- Ingestion is the foundation of all data engineering work.  
- Choose between batch and streaming ingestion based on workload requirements.  
- Use managed connectors where possible to reduce custom engineering.  
- Leverage object storage for scalable, secure data movement.  
- Monitor ingestion pipelines continuously to ensure reliability.  
- Practice strong data ethics, security, and compliance.  
- Invest in orchestration and DataOps for long-term pipeline health.

---
