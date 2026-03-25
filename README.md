# 🚀 End-to-End Data Engineering Pipeline using Databricks & AWS S3

## 📌 Project Overview

This project demonstrates an end-to-end **data engineering pipeline** built using **Databricks** and **AWS S3**, following the **Medallion Architecture (Bronze, Silver, Gold layers)**.

The pipeline processes raw business data (sales, product pricing, and related datasets), cleans and standardizes it, and produces analytics-ready datasets for reporting and dashboarding.

This project is based on a guided implementation from Codebasics and enhanced with practical understanding and dashboard creation.

---

## 🗂️ Dataset Description

The dataset simulates real-world business data and includes:

* 📦 Product data (product codes, mappings)
* 💰 Gross price data (contains invalid and inconsistent values)
* 📅 Date/month column (multiple inconsistent formats)

### ⚠️ Data Challenges:

* Dates stored in **multiple formats**
* Price column contains:

  * Negative values
  * "unknown" values
* Missing/incorrect product identifiers

---

## 🧱 Architecture

The project follows **Medallion Architecture**:

```id="y2r7s1"
AWS S3 → Bronze → Silver → Gold → Dashboard
```

* ☁️ **AWS S3** → Raw data storage
* 🥉 **Bronze Layer** → Raw ingested data
* 🥈 **Silver Layer** → Cleaned & transformed data
* 🥇 **Gold Layer** → Business-ready data
* 📊 **Dashboard** → Insights

---

## ⚙️ Tech Stack

* Databricks (Lakehouse Platform)
* PySpark
* SQL
* Delta Lake
* AWS S3

---

## 🔄 Data Pipeline Workflow

### 🔹 1. Data Ingestion (Bronze Layer)

* Uploaded raw datasets to **AWS S3**
* Connected S3 with Databricks
* Loaded raw data into **Bronze Delta tables**
* No transformation applied (raw format preserved)

---

### 🔹 2. Data Transformation (Silver Layer)

Performed key real-world data cleaning:

#### 📅 Date Standardization

* Used `try_to_date()` with multiple formats
* Applied `coalesce()` to select valid date
* Converted all dates into a **uniform format**

#### 💰 Price Cleaning

* Converted negative values → positive
* Replaced "unknown"/invalid values → 0
* Cast values to numeric format

#### 🔗 Data Enrichment

* Mapped product codes to proper product IDs
* Joined multiple datasets for consistency

---

### 🔹 3. Data Aggregation (Gold Layer)

* Created business-level tables
* Generated KPIs:

  * Total Revenue
  * Product Performance
  * Sales Trends
* Optimized tables for reporting

---

## 📊 Dashboard

Developed an interactive dashboard in Databricks to visualize:

* 📈 Sales trends over time
* 💰 Total revenue
* 📦 Top-performing products
* ⚠️ Low-performing products

### Dashboard Features:

* KPI cards (Revenue, Orders, Quantity, Avg Order Value)
* Time-series analysis
* Product-level insights
* Interactive filters (date, category)

---

## 🎯 Key Learnings

* Built an end-to-end data pipeline using Databricks
* Implemented Medallion Architecture (Bronze → Silver → Gold)
* Handled real-world messy data (dates, invalid values)
* Integrated AWS S3 with Databricks
* Performed data transformation using PySpark & SQL
* Created analytics dashboards


---


## 👤 Author

**Niranjan N**
