# SQL_Swiggy_Sales

Here is the complete README.md file for your GitHub repository. I have structured it using Markdown best practices, including a clean layout, technical highlights, and the project's business value.

Swiggy Food Delivery Analytics: End-to-End SQL Pipeline
📌 Project Overview
This project demonstrates a complete data engineering and analytics workflow using a Swiggy food delivery dataset. The pipeline transforms raw, unorganized data into a robust Dimensional Model (Star Schema) to enable high-performance Business Intelligence (BI) reporting and advanced market analysis.

Key Objectives:
Data Quality Assurance: Comprehensive cleaning, duplicate removal, and outlier handling.

Dimensional Modeling: Implementation of a Star Schema with 5 Dimension tables and 1 central Fact table.

KPI Development: Calculation of core business metrics (Revenue, AOV, Order Volume).

Advanced Growth Analysis: Identifying market expansion opportunities and customer behavior patterns.

🏗️ Data Architecture (Star Schema)
To optimize query performance and ensure data integrity, the raw data was decomposed into a Star Schema. This structure allows for fast aggregations and clear descriptive filtering.

Fact Table: fact_swiggy_orders (Transactional metrics: Price, Ratings, IDs).

Dimension Tables:

dim_date: Temporal attributes (Year, Month, Quarter, Day of Week).

dim_location: Geographic hierarchy (State, City, Location).

dim_restaurant: Entity information.

dim_category: Product categorization (Cuisines).

dim_dish: Item-level details.

🛠️ SQL Workflow Breakdown
1. Data Cleaning & QA
Before modeling, the data underwent a rigorous auditing process:

Null & Blank Detection: Identified gaps in critical business dimensions.

Deduplication: Used CTEs and ROW_NUMBER() to purge identical records while maintaining data lineage.

Normalization: Corrected invalid ratings and price outliers to ensure statistical accuracy.

2. ETL Process (Extract, Transform, Load)
Surrogate Keys: Generated using IDENTITY columns for efficient indexing.

Temporal Enrichment: Enriched the date dimension with specific attributes like Month_Name and Quarter.

Data Integrity: Used INNER JOINs during the load phase to ensure only fully-dimensional rows reach the fact table.

3. Business Intelligence Insights
The analysis layer provides actionable insights for stakeholders:

Geographic Opportunities: Identified "Under-the-radar" cities (e.g., Panaji, Gurgaon) with high Average Order Value (AOV) but moderate volume.

Customer Spending: Segmented revenue into price buckets to inform promotional strategies.

Temporal Patterns: Discovered peak ordering days and monthly growth rates using Window Functions (LAG).

Restaurant Scorecards: Ranked vendors by a combination of revenue, volume, and rating consistency.

📈 Key SQL Techniques Applied
Window Functions: ROW_NUMBER() for deduplication and LAG() for Month-over-Month (MoM) growth calculations.

CTEs (Common Table Expressions): For modular, readable, and organized code structure.

Aggregations & Grouping: Complex GROUP BY operations combined with HAVING filters to ensure statistical significance.

Data Type Casting: Strategic use of CAST and CONVERT to handle financial precision and prevent integer truncation.

Advanced Filtering: Implemented OFFSET / FETCH for standard-compliant pagination.

🚀 How to Use
Environment: Designed for Microsoft SQL Server (T-SQL).

Execution: Run the scripts in the following order:

Step 1: Run the Data Cleaning section to profile and sanitize the raw landing table.

Step 2: Execute the Dimensional Modeling section to build the schema and trigger the ETL.

Step 3: Run BI & KPI Development for high-level metrics.

Step 4: Execute Intermediate Analysis for deep-dive business insights.

Author: David Stocco

Date: February 10, 2026

Project: Swiggy Data Analysis Portfolio
