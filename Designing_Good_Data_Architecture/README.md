## 🧠 Designing Good Data Architecture  

### 📄 Overview  
This week focused on how data architecture underpins every data-engineering system and how the right architectural choices drive scalability, reliability, and business value.
The chapter explored classical and modern data architectures — from monoliths and microservices to data warehouses, data lakes, and the data mesh — and explained how to design systems that balance flexibility, performance, and governance.

---

### 🏗️ Key Concepts and Topics Covered  

#### **1️⃣ Major Architecture Concepts**
- **Monolith vs Microservices:** monolithic systems are tightly coupled and hard to scale; microservices separate concerns into independent services communicating through APIs or events.  
- **Tight vs Loose Coupling:** loose coupling improves modularity and maintainability.  
- **Single- vs Multi-Tier:** three-tier (presentation, logic, data) enables clear separation of concerns.  
- **User Access:** single- vs multi-tenant design for shared cloud systems.  

#### **2️⃣ Event-Driven Architectures**
- Events flow between producers, routers, and consumers.  
- Enables asynchronous communication and fault tolerance across distributed systems.  

#### **3️⃣ Project Types – Brownfield & Greenfield**
- **Brownfield:** refactoring existing architecture → requires empathy, incremental change, and the *strangler pattern*.  
- **Greenfield:** fresh start → risk of “shiny object syndrome,” but fosters innovation.  

#### **4️⃣ Data Warehouse Architectures**
- Centralized data hub for reporting/analytics.  
- **ETL/ELT workflows:** extract → transform/load into staging → warehouse → data marts.  
- **Cloud Data Warehouse:** Redshift, BigQuery, Snowflake separate compute & storage, scale on-demand.

#### **5️⃣ Data Lake & Lakehouse**
- Data Lake 1.0 (HDFS): raw storage but lacked governance → “data swamp.”  
- **Lakehouse:** merges lake flexibility with warehouse reliability (ACID transactions).  
- Led to **Modern Data Stack:** modular cloud services — pipelines, storage, transformation, BI.

#### **6️⃣ Lambda and Kappa Architectures**
- **Lambda:** batch + stream layers merged in serving layer.  
- **Kappa:** stream-only approach using same system for batch & real-time.  
- Goal → unified batch/stream model (Dataflow / Beam).

#### **7️⃣ IoT Architecture**
- IoT devices → gateways → stream processing → storage → ML/reports.  
- Handles late-arriving data, schema differences, and connectivity issues.

#### **8️⃣ Data Mesh**
- Introduced by Zhamak Dehghani.  
- **Four pillars:**  
  1. Domain-oriented decentralized ownership  
  2. Data as a product  
  3. Self-serve data platform  
  4. Federated computational governance  

#### **9️⃣ Design Collaboration**
- Data architecture is not built in a vacuum — requires engineers + data architects + business stakeholders.  
- Evaluate trade-offs for storage, compute, streaming, and governance.  

---

### 🧩 Main Takeaways  
- **Architecture = foundation of data engineering** — decisions about integration, processing, and storage directly affect scalability and ROI.  
- **Flexibility + modularity beat monolithic designs.**  
- **Modern architectures** (e.g., data mesh & lakehouse) evolve from traditional warehousing to support domain ownership and real-time analytics.  
- Data engineers must grasp architectural trade-offs to design systems fit for business needs and future growth.

---

### 🧭 Reflection  
This week deepened my understanding of **how architecture decisions translate into real-world data engineering systems**.  
From classical ETL pipelines to modern data mesh governance, I learned how each pattern addresses specific scalability, performance, and collaboration challenges in data-driven organizations.
