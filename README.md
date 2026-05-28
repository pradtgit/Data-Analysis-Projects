# Data-Analysis-Projects

This repository contains the data analysis and data engineering projects I worked on using SQL, Tableau, Excel and Microsoft Azure. Through these projects, I practiced working with raw data, cleaning and transforming datasets, writing SQL queries, building dashboards, creating business insights from data and building a cloud-based data engineering pipeline.

These projects strengthen my understanding of data analysis, data warehousing, business intelligence, reporting workflows, data engineering, cloud ETL and end-to-end data pipeline development.

---

## Projects

### 1. Data Warehousing Project Using SQL

In this project, I worked on building a SQL Server data warehouse using raw CRM and ERP datasets. I loaded the data from CSV files, cleaned and standardized it and organized it into a structured data warehouse.

I learned how to follow the Bronze, Silver and Gold layer approach. The Bronze layer stores raw source data, the Silver layer stores cleaned and transformed data and the Gold layer contains final business-ready views for analysis.

I also worked on creating stored procedures, applying data quality checks and building a Star Schema using customer, product and sales data.

**What I worked on**

* Loaded raw CRM and ERP CSV files into SQL Server
* Created Bronze, Silver and Gold layers
* Cleaned and standardized customer, product, sales and location data
* Built stored procedures for reusable data loading
* Created Gold layer dimension and fact views
* Designed a Star Schema for reporting and analysis
* Performed data quality checks to validate the final data model

**What I learned**

* How data warehousing works in real projects
* How to clean and transform messy source data using SQL
* How to separate raw, cleaned and reporting-ready data
* How to design dimension and fact tables
* How to validate data quality before analysis

**Tools & Technologies**

[SQL Server | T-SQL | SSMS | ETL | Stored Procedures | DDL | BULK INSERT | Data Warehousing | Star Schema | Data Cleaning | Data Quality Checks | CRM | ERP]

---

### 2. Data Analysis Using SQL

In this project, I worked on analyzing the final Gold layer dataset created from my data warehousing project. The goal was to explore the data, calculate business metrics and create SQL reports for customer and product analysis.

Wrote SQL queries to explore database tables, analyze sales performance, compare products and customers, calculate KPIs and create final reporting views.

I also learned how SQL can be used not only for querying data, but also for business analysis, segmentation and reporting.

**What I worked on**

* Explored database tables, columns and schemas
* Analyzed dimensions such as customers, products and categories
* Calculated KPIs such as total sales, total orders, quantity and customers
* Performed ranking analysis for top products and customers
* Analyzed sales trends over time
* Used cumulative analysis to calculate running totals and moving averages
* Segmented customers into VIP, Regular and New groups
* Segmented products into High Performer, Mid-Range and Low Performer groups
* Created final customer and product report views

**What I learned**

* How to write SQL queries for business analysis
* How to use joins, aggregations, CTEs and subqueries
* How to use window functions such as RANK, LAG and SUM OVER
* How to calculate KPIs from sales data
* How to create reusable SQL views for reporting
* How to turn raw business data into useful insights

**Tools & Technologies**

[SQL Server | T-SQL | DDL | DQL | Joins | CTEs | Subqueries | Window Functions | RANK | LAG | SUM OVER | AVG OVER | CASE | DATEDIFF | DATETRUNC | Views | KPI Analysis | Customer Segmentation | Product Segmentation]

---

### 3. Azure Data Engineering Pipeline for Olympics Data
In this project, I worked on building an end-to-end cloud data engineering pipeline on Microsoft Azure using Tokyo Olympics data. I ingested raw CSV files from GitHub, stored them in Azure Data Lake Storage Gen2, transformed the data using Azure Databricks and PySpark and performed SQL-based analysis using Azure Synapse Analytics.

This project helped me understand how different Azure services work together to move, store, transform and analyze data in a structured cloud data pipeline.


What I worked on

Created Azure Data Factory pipelines to ingest raw CSV files from GitHub
Stored raw data in Azure Data Lake Storage Gen2
Organized data into raw and transformed storage layers
Used Azure Databricks and PySpark to clean and transform the data
Saved transformed data back into Azure Data Lake Storage Gen2
Connected Azure Synapse Analytics to the transformed data
Wrote SQL queries to analyze the Tokyo Olympics dataset
Built an end-to-end ETL workflow using Azure cloud services

What I learned

How to build an end-to-end Azure data engineering workflow
How to create data ingestion pipelines using Azure Data Factory
How to store raw and transformed data in Azure Data Lake Storage Gen2
How to use PySpark in Azure Databricks for data transformation
How to query transformed data using Azure Synapse Analytics
How cloud services work together in a scalable data pipeline

Tools & Technologies

[Azure Data Factory | Azure Data Lake Storage Gen2 | Azure Databricks | PySpark | Apache Spark | Azure Synapse Analytics | SQL | Python | GitHub | CSV Files | ETL | Data Engineering | Cloud Data Pipeline]

---

### 4. Airbnb NYC Tableau Dashboard

In this project, I worked on building an interactive Tableau dashboard to analyze Airbnb listings across New York City. The dashboard helps users understand Airbnb activity across different neighborhood groups such as Manhattan, Brooklyn, Queens, Bronx and Staten Island.

I used Tableau to create charts, filters, maps and KPI cards to analyze bookings, prices, reviews, room types and top-performing hosts.

This project helped me learn how to present data visually and make dashboards interactive for better business understanding.

**What I worked on**

* Built an interactive Tableau dashboard using Airbnb NYC data
* Created KPI cards for total hosts, neighborhoods and average reviews
* Analyzed bookings by neighborhood group and room type
* Compared average prices across neighborhoods and boroughs
* Created charts for monthly booking trends and yearly reviews
* Built a map view to show geographic distribution
* Added filters for neighborhood group and room type
* Designed the dashboard layout for clear storytelling

**What I learned**

* How to create interactive dashboards in Tableau
* How to use filters to explore data dynamically
* How to choose the right chart types for different business questions
* How to use maps for location-based analysis
* How to present business insights through visual storytelling

**Tools & Technologies**

[Tableau Public | Microsoft Excel | CSV Dataset | Data Cleaning | Data Visualization | Interactive Dashboard | Map Visualization | Treemap | Donut Chart | KPI Cards | Business Intelligence]

---

### 5. Coffee Sales Dashboard Using Excel

In this project, I worked on creating an Excel dashboard to analyze coffee sales data. The dataset included order details, customer information and product information.

I cleaned the data, used lookup formulas to combine different tables, calculated sales and created PivotTables and PivotCharts. I also added slicers and a timeline filter to make the dashboard interactive.

This project helped me understand how Excel can be used for data cleaning, sales analysis and business dashboarding.

**What I worked on**

* Cleaned and prepared raw coffee sales data
* Used XLOOKUP and INDEX MATCH to combine customer and product details
* Created a sales column using unit price and quantity
* Standardized coffee type and roast type values
* Converted the dataset into an Excel table
* Created PivotTables and PivotCharts
* Built an interactive Excel dashboard
* Added slicers and a timeline filter for dynamic analysis
* Analyzed sales by coffee type, country, customer, roast type, size and loyalty card status

**What I learned**

* How to clean and organize data in Excel
* How to use lookup formulas to combine datasets
* How to create PivotTables and PivotCharts
* How to build interactive dashboards using slicers and timelines
* How to analyze sales performance from different business angles

**Tools & Technologies**

[Microsoft Excel | XLOOKUP | INDEX MATCH | IF Formulas | PivotTables | PivotCharts | Slicers | Timeline Filter | Excel Tables | Data Cleaning | Sales Analysis | Dashboard Design]

---

## Skills I Practiced

Through these projects, I practiced:

* Data Cleaning
* Data Transformation
* SQL Querying
* Data Warehousing
* ETL Development
* Cloud Data Engineering
* Azure Data Factory Pipeline Development
* Azure Data Lake Storage Gen2
* Azure Databricks
* PySpark and Apache Spark Transformations
* Azure Synapse Analytics
* Raw and Transformed Data Layering
* Star Schema Modeling
* KPI Calculation
* Business Analysis
* Customer Segmentation
* Product Segmentation
* Dashboard Design
* Data Visualization
* Interactive Reporting
* Business Insight Generation

---
