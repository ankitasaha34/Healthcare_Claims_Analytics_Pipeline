# 🏥 Healthcare Claims Analytics Pipeline

## 📌 Overview

This project demonstrates an end-to-end **healthcare claims analytics pipeline**, transforming raw claims data into **governed, analytics-ready datasets** and generating **business insights** related to cost drivers, utilization trends, and operational efficiency.

The project emphasizes **analytics engineering best practices**, including data cleaning, quality validation, fact–dimension modeling, SQL-based analysis, visualization, and baseline machine learning workflow exposure.

Link to the Dataset - https://www.kaggle.com/datasets/leandrenash/enhanced-health-insurance-claims-dataset?resource=download
---

## 📂 Dataset Description

The dataset used in this project is a **synthetic healthcare insurance claims dataset** sourced from Kaggle.

Each record represents a **single insurance claim**, including patient demographics, provider details, financial attributes, and claim lifecycle information.

### Dataset Characteristics

* **Total Records:** 4,500
* **Granularity:** One row per insurance claim
* **Nature:** Synthetic (no real patient or provider data)
* **Domain:** Health insurance / claims processing

### Key Fields

* **Identifiers:** `ClaimID`, `PatientID`, `ProviderID`
* **Financial Data:** `ClaimAmount`, `PatientIncome`
* **Temporal Data:** `ClaimDate`
* **Clinical Context:** `DiagnosisCode`, `ProcedureCode`
* **Operational Attributes:** `ClaimStatus`, `ClaimType`, `ClaimSubmissionMethod`
* **Patient Attributes:** Age, gender, marital status, employment status
* **Provider Attributes:** Specialty, location

> Although synthetic, the dataset closely mirrors real-world healthcare claims structures commonly used for analytics, reporting, and operational monitoring.

---

## 🏗️ Architecture & Data Model
<img width="622" height="397" alt="image" src="https://github.com/user-attachments/assets/8ebab139-7dc2-4ce5-9925-ba6553e6c09a" />



---

## 🔄 Data Processing & Governance

### ETL & Standardization

* Standardized date and numeric fields for reliable aggregation
* Cleaned categorical attributes for consistent grouping
* Enforced explicit data types to support analytics and modeling

### Data Quality Validation

* **0 duplicate claims**
* **0 missing claim IDs**
* **0 missing claim dates**
* **0 negative claim amounts**
* **0 future-dated claims**

### Governance & Integrity

* Claim-level deduplication enforced using `ClaimID`
* Referential integrity validated across fact and dimension tables
* Curated datasets saved for downstream reuse

---

## 🧱 Data Modeling

### Fact Table

**`fact_claims`** (4,500 rows)

* ClaimID
* PatientID
* ProviderID
* ClaimDate
* ClaimAmount
* ClaimStatus
* ClaimType
* DiagnosisCode
* ProcedureCode
* ClaimSubmissionMethod

### Dimension Tables

**`dim_patients`** (4,500 rows)

* Patient demographics and socioeconomic attributes

**`dim_providers`** (4,500 rows)

* Provider specialty and geographic location

> In this dataset, each claim maps to a unique patient and provider, resulting in dimensions with the same row count as the fact table. The modeling approach is designed to scale to real-world scenarios where multiple claims map to the same entities.

---

## 📊 Analytics & Business Insights

### Cost & Utilization Analysis

* Identified **provider specialties** responsible for the highest total claim spend
* Found that **claim volume**, rather than extreme per-claim costs, was the primary cost driver

### Temporal Trends

* Monthly trend analysis revealed **seasonal cost patterns**, with higher utilization toward year-end
* Monthly costs remained within a stable operating range, supporting budgeting and forecasting

### Operational Efficiency

* Claim status analysis showed a **consistently high proportion of pending claims** across all claim types
* Highlights opportunities to improve claims processing efficiency and turnaround time

---

## 📈 Visualizations

The project includes business-focused visualizations:

* Total claim amount by provider specialty
* Claim status distribution (Approved / Denied / Pending)
* Monthly claim cost trends

These visualizations support decision-making related to cost management, operational performance, and planning.

---

## 🤖 Machine Learning (Baseline)

A baseline **logistic regression model** was built to predict claim approval status.

* **Accuracy:** ~66%
* Demonstrated ML workflow integration using analytics-ready data
* Identified **class imbalance and feature limitations**, informing future model improvements

> This model is intended to demonstrate **machine learning process familiarity**, not production-grade predictive performance.

---

## 🛠️ Tools & Technologies

* **Python:** Pandas, NumPy
* **SQL:** DuckDB
* **Visualization:** Matplotlib
* **Machine Learning:** Scikit-learn
* **Environment:** Jupyter Notebook

---

## 🎯 Key Takeaways

* Built a complete analytics pipeline from raw data to business insights
* Applied data quality and governance principles to healthcare claims data
* Designed analytics-ready fact and dimension tables for scalable reporting
* Translated analytical outputs into actionable operational and financial insights


* Tighten this into a **recruiter-skim version**
* Add **chart image placeholders**
* Align this **word-for-word with your resume bullets**
* Create a **30–60 second GitHub walkthrough script**

Just tell me what you’d like to do next 💪
