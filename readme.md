# Governed Data Lakehouse (Databricks) — Secure Analytics Platform

An end-to-end governed data lakehouse built on **Databricks** to deliver **secure, compliant, and analytics-ready** datasets.  
The platform implements **Bronze → Silver → Gold** Delta pipelines with automated validation, governance controls via **Unity Catalog**, and enterprise metadata + lineage using **Microsoft Purview**.

> ✅ Timeline: Apr 2025 – Oct 2025  
> ✅ Focus: Data engineering + governance + secure BI consumption

---

## Key Features

### 1) Medallion Architecture (Bronze / Silver / Gold)
- Built Delta Lake pipelines across **Bronze**, **Silver**, and **Gold** layers
- Implemented **data quality validation** (null checks, schema checks, business rules)
- Scheduled **automated refresh** and incremental loads where applicable

### 2) Governance & Security (Unity Catalog)
- Enforced access control using **Unity Catalog RBAC**
- Implemented **column-level masking** for sensitive fields (PII) to support **GDPR-style protections**
- Structured permissions by personas (e.g., Analyst, Data Engineer, Admin)

### 3) Metadata, Lineage & Business Glossary (Microsoft Purview)
- Integrated **Microsoft Purview** for:
  - Data lineage tracking
  - Glossary management
  - Business term classification and discoverability

### 4) Analytics Consumption (Databricks SQL Warehouse + Power BI)
- Exposed curated **Gold views** through **Databricks SQL Warehouse**
- Enabled downstream usage in analytics tools like **Power BI** via governed views

---

## Architecture Overview

```text
Sources
  └── Ingestion (Batch/Auto Loader/ELT)
        └── Bronze (raw, append-only)
              └── Validation + Standardization
                    └── Silver (cleaned, conformed)
                          └── Aggregation + Business logic
                                └── Gold (curated views/tables)
                                      └── Databricks SQL Warehouse
                                            └── Power BI / Analytics
Governance (Unity Catalog) applied across layers + masking policies for PII
Purview captures lineage + glossary + classification
