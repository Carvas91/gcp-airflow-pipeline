# CP Data Engineering – Healthcare Revenue Cycle Management (RCM)

## 📌 Project Overview

This project builds a data lake in **Google Cloud Platform (GCP)** for **Revenue Cycle Management (RCM)** in the healthcare sector. The solution centralizes and transforms data from multiple sources (hospital systems, insurance claims, and medical coding APIs) to streamline billing, claims processing, and revenue tracking.

---

## 🧱 Architecture Summary

This project implements the **Medallion Architecture** with modern data engineering practices:

- 🥉 **Bronze Layer** – Raw ingested data (EMR, claims, API pulls)
- 🥈 **Silver Layer** – Cleaned, transformed, and standardized tables
- 🥇 **Gold Layer** – Business-ready tables used for reporting and analytics

All processes are orchestrated using **Apache Airflow (Cloud Composer)** and run in a scalable, monitored environment.

---

## ☁️ GCP Services Used

- **Cloud Storage (GCS)** – Raw/processed file storage  
- **BigQuery** – Data warehouse for analytics  
- **Dataproc (Spark)** – Distributed data processing  
- **Cloud Composer (Airflow)** – Workflow orchestration  
- **Cloud SQL (MySQL)** – Source database (EMR systems)  
- **Cloud Build + GitHub** – CI/CD automation  

---

## 🛠️ Key Engineering Techniques

### 🔁 Metadata-Driven Pipelines
- Config-based ETL, no hardcoding  
- Scalable & reusable across sources

### 📚 Slowly Changing Dimensions (SCD Type 2)
- Tracks history in dimensional tables  
- Maintains auditability of patient/provider updates

### 🏥 Common Data Model (CDM)
- Standardizes schema across multiple hospitals  
- Supports interoperability and unified analytics

### 🧪 Data Validation & Logging
- Real-time error tracking & logging  
- Validations for nulls, duplicates, and type mismatches

### 🔐 Access & Compliance
- IAM access control  
- HIPAA-aligned retention and handling policies

---

## 🔄 RCM Workflow – What It Enables

1. **Patient Visit** → registration & insurance verification  
2. **Service Provided** → treatments & billing  
3. **Billing Generation** → itemized medical bill  
4. **Claims Review** → insurance approval/rejection  
5. **Payment Follow-up** → patient collections  
6. **Performance KPIs** → dashboards for optimization

---

## 🧩 Data Sources

| Source | Description | Format |
|--------|-------------|--------|
| **EMR Systems** | Hospital A & B (Cloud SQL) | MySQL tables |
| **Claims Files** | Monthly insurance claims | CSV |
| **CPT API** | Procedure codes | REST API |
| **ICD API** | Disease classifications | REST API |
| **NPI API** | Provider identifiers | REST API |

---

## 🔄 Data Engineering Workflow

1. **Extract**
   - PySpark jobs pull data from Cloud SQL (EMR)
   - Flat file ingestion for claims (GCS)
   - Public APIs for CPT, ICD, NPI

2. **Transform**
   - Normalize formats
   - Handle nulls, duplicates, types
   - Build fact & dimension tables

3. **Load**
   - Store curated data in BigQuery (silver/gold)

4. **Orchestrate**
   - Airflow DAGs ensure dependency control and retries

5. **Visualize**
   - Enable dashboards showing:
     - Revenue trends
     - Claim approval rates
     - Patient billing performance

---

## ✅ Expected Outcomes

- ⚙️ Automated pipelines for RCM data ingestion & transformation  
- 🧠 Structured data warehouse with analytical tables (BigQuery)  
- 📊 KPI dashboards for financial visibility and process optimization  
- 🚀 Hands-on experience with **GCP, Airflow, Spark, CI/CD, and HIPAA-aware data handling**

---

## 🧠 Why It Matters

**Revenue Cycle Management** is critical for hospital profitability. This project demonstrates how modern data engineering enables healthcare organizations to reduce manual errors, accelerate claims processing, and improve overall cash flow visibility.

---

## 📁 Repository Structure (example)
