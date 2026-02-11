# 🍔 SQL Swiggy Sales Analysis  
### End-to-End Data Engineering & Business Intelligence Project

---

## 📌 Project Overview

This project demonstrates a **complete SQL-based data analytics pipeline** using a Swiggy food delivery dataset.  
The goal is to transform raw transactional data into a **clean, scalable Star Schema** and extract **business-ready insights** for decision-making.

The project mirrors real-world **Data Analyst / BI workflows**, including data cleaning, modeling, KPI design, and analytical reporting.

---

## 🎯 Business Objectives

- Ensure **data quality and consistency** through systematic cleaning and validation  
- Design a **Dimensional Model (Star Schema)** optimized for analytics  
- Build **core KPIs** used by food delivery platforms  
- Identify **growth opportunities**, demand patterns, and restaurant performance  

---

## 🏗️ Data Architecture — Star Schema

To improve query performance and analytical clarity, the raw dataset was decomposed into a **Star Schema**.

### 🟡 Fact Table
- **`fact_swiggy_orders`**
  - Transactional metrics: `Price_INR`, `Rating`, `Rating_Count`
  - Foreign keys to all dimensions

### 🔵 Dimension Tables
- **`dim_date`** – Year, Month, Quarter, Day of Week  
- **`dim_location`** – State, City, Area  
- **`dim_restaurant`** – Restaurant metadata  
- **`dim_category`** – Cuisine / food category  
- **`dim_dish`** – Individual dish details  

This structure enables **fast aggregations, flexible slicing, and BI tool compatibility**.

---

## 🛠️ SQL Workflow Breakdown

### 1️⃣ Data Cleaning & Quality Assurance
- Null and blank value detection  
- Deduplication using `ROW_NUMBER()` and CTEs  
- Outlier handling for invalid prices and ratings  
- Data type normalization for financial precision  

### 2️⃣ ETL Process (Extract, Transform, Load)
- Surrogate keys created with `IDENTITY`  
- Enriched date dimension (Month name, Quarter, Weekday)  
- Referential integrity enforced with controlled joins  
- Only fully valid records loaded into the fact table  

### 3️⃣ Business Intelligence & Analytics
- Revenue & Average Order Value (AOV) analysis  
- City-level and restaurant-level performance ranking  
- Time-based trend analysis (daily, monthly, quarterly)  
- Market expansion opportunity detection  

---

## 📊 Key Insights Generated

- 📍 **Geographic opportunities**: Cities with high AOV but moderate order volume  
- 📈 **Temporal trends**: Peak ordering days and monthly growth patterns  
- 🍽️ **Restaurant scorecards**: Revenue, volume, and rating consistency  
- 💰 **Pricing behavior**: Revenue distribution across price buckets  

---

## 🧠 SQL Techniques Applied

- **CTEs (Common Table Expressions)** for modular, readable logic  
- **Window Functions**:
  - `ROW_NUMBER()` for deduplication  
  - `LAG()` for Month-over-Month growth analysis  
- **Advanced Aggregations** with `GROUP BY` and `HAVING`  
- **Data Type Casting** using `CAST` / `CONVERT` for accuracy  
- **Pagination & Filtering** with `OFFSET / FETCH`  

---

## 🚀 How to Run the Project

**Environment:** Microsoft SQL Server (T-SQL)

### Execution Order
1. **Data Cleaning & Profiling**  
2. **Dimensional Modeling (Star Schema creation)**  
3. **ETL Load into Fact Table**  
4. **KPI & BI Analysis Queries**  
5. **Advanced Business Insights**

---

## 📂 Repository Structure

```text
├── 01_data_cleaning.sql
├── 02_dimensional_model.sql
├── 03_etl_load.sql
├── 04_kpi_analysis.sql
├── 05_advanced_insights.sql
└── README.md

👤 Author

David Stocco
📅 February 2026
🔗 GitHub https://github.com/davidstocco2024-cell

🔗 LinkedIn https://www.linkedin.com/in/david-stocco-35ba40278/

📢 Final Notes

This project reflects real-world SQL analytics, bridging data engineering and business intelligence.
Designed to showcase clean code, scalable modeling, and analytical depth.

Feedback and collaboration ideas are welcome.

Project Type: SQL Data Analysis & Modeling Portfolio
Focus Areas: Data Quality, Dimensional Modeling, Business Intelligence
