# 🚀 End-to-End Data Engineering Pipeline using Databricks & AWS S3

## 📌 Project Overview

This project demonstrates a scalable **data engineering pipeline** built using **Databricks** and **AWS S3**, designed using a **Medallion Architecture (Bronze, Silver, Gold)** with a **multi-organization (Parent–Child) data model**.

The pipeline ingests raw data from S3, processes it through layered transformations, and delivers business-ready insights via dashboards and serving layer tools.

---

## 🏗️ Architecture Overview

![Architecture](project_architecture.png)

### Key Components:

* ☁️ **AWS S3**

  * Stores raw data and archive data
  * Acts as the primary data source

* ⚙️ **Lakeflow Jobs (Databricks Workflows)**

  * Automates data ingestion and transformation
  * Orchestrates pipeline execution

* 🥉 **Bronze Layer**

  * Raw data ingestion from S3
  * Stores unprocessed data for traceability

* 🥈 **Silver Layer**

  * Cleans and transforms data
  * Handles:

    * Date standardization
    * Invalid values (negative, null, unknown)
    * Data enrichment via joins

* 🥇 **Gold Layer**

  * Aggregated business data
  * Generates KPIs and analytics tables

---

## 🏢 Multi-Organization Data Model

### 🔹 Child Company

* Owns the complete pipeline:

  * Bronze → Silver → Gold
* Processes and prepares cleaned data

### 🔹 Parent Company

* Consumes **Gold layer data** from child company
* Performs additional aggregation
* Maintains centralized **analytics table**

👉 This simulates a real-world **data sharing and consolidation architecture**

---

## 📊 Serving Layer

The final data is consumed through:

* 📊 **Dashboards (Databricks SQL)**
* 🤖 **Genie / BI tools**
* 📈 Business reporting systems

👉 Enables decision-making using clean, structured data

---

## ⚙️ Tech Stack

* Databricks (Lakehouse Platform)
* PySpark
* SQL
* Delta Lake
* AWS S3
* Databricks Workflows (Lakeflow Jobs)

---

## 🔄 Data Pipeline Workflow

### 🔹 1. Data Ingestion

* Raw data is stored in **AWS S3**
* Lakeflow Jobs ingest data into Bronze tables

---

### 🔹 2. Data Transformation

* Bronze → Silver:

  * Cleaned inconsistent date formats
  * Fixed invalid price values
  * Removed null/unknown data
  * Joined datasets for enrichment

---

### 🔹 3. Data Aggregation

* Silver → Gold:

  * Created KPI tables
  * Aggregated revenue and product metrics

---

### 🔹 4. Data Sharing

* Gold data from **Child Company** is shared with **Parent Company**
* Parent layer performs further aggregation

---

### 🔹 5. Data Consumption

* Data exposed via:

  * Dashboards
  * BI tools
  * Analytics platforms

---

## 📊 Dashboard Features

* 📈 Sales trends
* 💰 Revenue metrics
* 📦 Product performance
* ⚠️ Low-performing products
* 🎛️ Interactive filters

---

## 🎯 Key Learnings

* Designed Medallion Architecture using Databricks
* Integrated AWS S3 with Databricks pipelines
* Built multi-layer ETL workflows
* Implemented Parent–Child data architecture
* Automated pipelines using Lakeflow Jobs
* Created analytics dashboards for business insights


---

## 👤 Author

**Niranjan N**
