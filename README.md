SQL_Swiggy_Sales
Swiggy Food Delivery Analytics — End-to-End SQL Pipeline
Project Overview

This project demonstrates a complete data engineering and analytics workflow using a Swiggy food delivery dataset.
The pipeline transforms raw, unstructured transactional data into a Dimensional Model (Star Schema) optimized for high-performance Business Intelligence (BI) reporting and analytical use cases.

The focus is on data quality, modeling correctness, and analytical depth, simulating a real-world analytics pipeline commonly found in production environments.

Project Objectives

Data Quality Assurance
Perform systematic data validation, null handling, deduplication, and outlier treatment.

Dimensional Modeling
Design and implement a Star Schema with clear separation of facts and dimensions.

KPI Development
Compute core business metrics such as Revenue, Average Order Value (AOV), and Order Volume.

Business Insight Generation
Identify growth opportunities, customer behavior patterns, and performance drivers across time, geography, and restaurants.

Data Architecture — Star Schema

To ensure query efficiency, scalability, and analytical clarity, the raw dataset was decomposed into a Star Schema.

Fact Table

fact_swiggy_orders
Stores transactional measures and foreign keys:

Order price

Ratings

Order identifiers

Surrogate dimension keys

Dimension Tables

dim_date
Year, Month, Month Name, Quarter, Day of Week

dim_location
State, City, Location

dim_restaurant
Restaurant-level attributes

dim_category
Cuisine and category classifications

dim_dish
Dish-level details

This structure enables fast aggregations, clean joins, and flexible slicing across analytical dimensions.

SQL Workflow Breakdown
1. Data Cleaning & Quality Assurance

Before modeling, the dataset underwent a structured auditing process:

Null and Blank Detection
Identified missing values in key analytical fields.

Deduplication
Used ROW_NUMBER() with CTEs to remove duplicate records while preserving data lineage.

Outlier & Invalid Value Handling
Normalized invalid ratings and price anomalies to ensure analytical accuracy.

2. ETL Process (Extract, Transform, Load)

Surrogate Keys
Generated using IDENTITY columns for efficient indexing and joins.

Temporal Enrichment
Enhanced the date dimension with derived attributes such as Month Name and Quarter.

Data Integrity Enforcement
Applied INNER JOINs during the load phase to ensure only fully dimensional records populate the fact table.

3. Business Intelligence & Analytics Layer

The analytical layer delivers actionable insights, including:

Geographic Opportunity Analysis
Identification of under-served cities with high AOV and moderate order volume.

Customer Spending Patterns
Revenue segmentation using price buckets to support pricing and promotion strategies.

Temporal Trend Analysis
Detection of peak ordering days and Month-over-Month growth using window functions.

Restaurant Performance Scorecards
Vendor ranking based on revenue, order volume, and rating consistency.

Key SQL Techniques Used

Window Functions
ROW_NUMBER() for deduplication
LAG() for Month-over-Month growth analysis

CTEs (Common Table Expressions)
Modular, readable, and maintainable query structure

Advanced Aggregations
Complex GROUP BY and HAVING logic for statistically meaningful insights

Data Type Management
Strategic use of CAST and CONVERT to preserve financial precision

Pagination & Filtering
OFFSET / FETCH for standards-compliant result pagination

How to Run the Project

Environment:
Microsoft SQL Server (T-SQL)

Execution Order:

Run the Data Cleaning & QA scripts on the raw landing table

Execute the Dimensional Modeling scripts to create the schema

Load the Fact Table via the ETL queries

Run BI & KPI queries for high-level metrics

Execute Advanced Analytical Queries for deeper insights

Author & Project Info

Author: David Stocco
Date: February 10, 2026
Project Type: SQL Data Analysis & Modeling Portfolio
Focus Areas: Data Quality, Dimensional Modeling, Business Intelligence
