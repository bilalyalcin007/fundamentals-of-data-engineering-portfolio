# Week 10 – Security and Privacy
**Fundamentals of Data Engineering – Joe Reis & Matt Housley**

---

## Week Objective

The goal of **Week 10** is to understand how **security and privacy** apply across the entire data engineering lifecycle.  
Rather than treating security as an afterthought, this chapter emphasizes that security must be embedded into **people, processes, and technology** from the beginning.

Security and privacy are not optional concerns for data engineers—they directly impact trust, compliance, and long-term system reliability.

---

## What I Focused On This Week

This week focused on how data engineers contribute to security and privacy by:

- Thinking defensively about data access and usage
- Applying least-privilege principles
- Protecting sensitive data at rest and in transit
- Monitoring systems for unusual or malicious behavior
- Understanding shared responsibility in cloud environments

These topics align with **Chapter 10: Security and Privacy**.

---

## People: The Human Factor in Security

One of the key takeaways is that **people are often the weakest link** in security.

Important ideas:
- Always assume credentials and systems are targets
- Practice defensive and negative thinking
- Question unusual requests for access or data
- Avoid collecting sensitive data unless absolutely necessary

Data engineers must stay vigilant because human mistakes often lead to breaches.

---

## Processes: Building Security Habits

Security should be a **habit**, not just a checklist.

Key practices include:
- Regular security reviews and training
- Avoiding “security theater” (compliance without real protection)
- Treating security as part of daily engineering work
- Planning for incident response and recovery

Good processes make secure behavior repeatable and reliable.

---

## Principle of Least Privilege

The **principle of least privilege** is a core security concept.

Key points:
- Users and systems should only have the access they need
- Access should be time-bound whenever possible
- Avoid granting broad administrative permissions
- Apply fine-grained access controls (row, column, cell level)

This principle protects both systems and sensitive data.

---

## Shared Responsibility in the Cloud

Cloud security follows a **shared responsibility model**:

- Cloud providers secure physical infrastructure
- Customers are responsible for configuration, access, and data protection

Most breaches occur due to **misconfigurations**, not cloud provider failures.

---

## Technology: Practical Security Measures

Important technical practices discussed include:
- Encrypting data at rest and in transit
- Avoiding insecure protocols
- Securing network access and firewall rules
- Applying patches and updates regularly
- Managing secrets properly (never hard-coding credentials)

Security must be built into systems, not added later.

---

## Logging, Monitoring, and Alerting

Security incidents are often discovered **after** they happen.

To reduce risk:
- Monitor access logs and system activity
- Track resource usage and billing anomalies
- Alert on unusual behavior
- Regularly review permissions and unused access

Observability is a critical part of DataOps and security.

---

## Key Takeaways

- Security and privacy apply to every stage of data engineering
- People, processes, and technology all matter
- Least privilege is a foundational principle
- Cloud security is a shared responsibility
- Monitoring and alerting help detect issues early
