# Data Analysis Using SQL

## Project Overview

This project focuses on SQL-based data analysis using an already prepared Gold layer dataset. The main goal of this project was to explore business data, analyze sales performance, understand customer and product behavior and create final SQL reporting views for business insights.

The data warehousing part, including the Bronze, Silver and Gold layer development was completed separately in my **Data Warehousing Project Using SQL** project. That project can be found in my GitHub profile under **Data-Analysis-Projects**.

In this project, I used the final Gold layer tables from that data warehouse and performed exploratory analysis, advanced analytics, segmentation, KPI calculations and reporting using SQL.

## Project Scope

This project covers the following SQL analytics work:

- Database and table setup for analysis
- Database structure exploration
- Dimension exploration
- Date range exploration
- Key measure analysis
- Magnitude analysis
- Ranking analysis
- Change over time analysis
- Cumulative analysis
- Performance analysis
- Data segmentation
- Part-to-whole analysis
- Customer report creation
- Product report creation

## Database Setup

The database setup is handled in:

```text
00_init_database.sql
```

This script creates the analytics database and prepares the Gold schema tables used in this project.

It creates:

```text
DataWarehouseAnalytics
gold.dim_customers
gold.dim_products
gold.fact_sales
```

It also loads the Gold layer CSV files into SQL Server using `BULK INSERT`.

The Gold layer data used here comes from my separate **Data Warehousing Project Using SQL** project.

## Data Used

This project uses three main Gold layer tables:

### `gold.dim_customers`

Contains customer information such as:

- Customer key
- Customer ID
- Customer number
- First name
- Last name
- Country
- Marital status
- Gender
- Birthdate
- Create date

### `gold.dim_products`

Contains product information such as:

- Product key
- Product ID
- Product number
- Product name
- Category
- Subcategory
- Maintenance flag
- Cost
- Product line
- Start date

### `gold.fact_sales`

Contains sales transaction information such as:

- Order number
- Product key
- Customer key
- Order date
- Shipping date
- Due date
- Sales amount
- Quantity
- Price

## SQL Script Execution Order

| Step | Script | Purpose |
|---|---|---|
| 1 | `00_init_database.sql` | Creates the analytics database, Gold schema and loads Gold tables |
| 2 | `01_database_exploration.sql` | Explores database tables, schemas, columns and metadata |
| 3 | `02_dimensions_exploration.sql` | Explores unique customer and product dimension values |
| 4 | `03_date_range_exploration.sql` | Finds date ranges, order history and customer age boundaries |
| 5 | `04_measures_exploration.sql` | Calculates key business metrics such as sales, quantity, orders, products and customers |
| 6 | `05_magnitude_analysis.sql` | Compares measures across dimensions such as country, gender, category and customer |
| 7 | `06_ranking_analysis.sql` | Identifies top and bottom performers using ranking logic |
| 8 | `07_change_over_time_analysis.sql` | Analyzes sales, customers and quantity trends over time |
| 9 | `08_cumulative_analysis.sql` | Calculates running totals and moving averages |
| 10 | `09_performance_analysis.sql` | Compares yearly product sales against average sales and previous year sales |
| 11 | `10_data_segmentation.sql` | Segments products and customers based on cost, spending and lifespan |
| 12 | `11_part_to_whole_analysis.sql` | Calculates category contribution to total sales |
| 13 | `12_report_customers.sql` | Creates the final customer report view |
| 14 | `13_report_products.sql` | Creates the final product report view |

## Analysis Performed

## 1. Database Exploration

Script:

```text
01_database_exploration.sql
```

I started by exploring the structure of the database using SQL metadata tables.

This included:

- Listing all tables in the database
- Checking table schemas
- Reviewing column names
- Checking data types
- Understanding the structure of the Gold layer tables

This step helped me understand what data was available before performing analysis.

## 2. Dimension Exploration

Script:

```text
02_dimensions_exploration.sql
```

I explored important dimension values in the customer and product tables.

This included:

- Unique customer countries
- Product categories
- Product subcategories
- Product names

This helped me understand the main business entities available for grouping and analysis.

## 3. Date Range Exploration

Script:

```text
03_date_range_exploration.sql
```

I analyzed date fields to understand the time period covered by the data.

This included:

- First order date
- Last order date
- Total order history in months
- Oldest customer birthdate
- Youngest customer birthdate
- Oldest and youngest customer age

This step helped define the historical scope of the sales and customer data.

## 4. Measures Exploration

Script:

```text
04_measures_exploration.sql
```

I calculated high-level business metrics to understand the overall business performance.

Metrics included:

- Total sales
- Total quantity sold
- Average selling price
- Total number of orders
- Total number of unique orders
- Total number of products
- Total number of customers
- Total number of customers who placed an order

I also created a combined metrics report using `UNION ALL` to show key business numbers in one result set.

## 5. Magnitude Analysis

Script:

```text
05_magnitude_analysis.sql
```

I compared business measures across different dimensions to understand distribution and performance.

This included:

- Total customers by country
- Total customers by gender
- Total products by category
- Average cost by category
- Total revenue by category
- Total revenue by customer
- Quantity sold by country

This analysis helped identify which customer groups, countries and product categories contributed most to the business.

## 6. Ranking Analysis

Script:

```text
06_ranking_analysis.sql
```

I used ranking analysis to identify top and bottom performers.

This included:

- Top 5 products by revenue
- Bottom 5 products by revenue
- Product ranking using `RANK()`
- Top 10 customers by revenue
- Customers with the fewest orders

This helped identify the strongest and weakest products and customers based on sales performance.

## 7. Change Over Time Analysis

Script:

```text
07_change_over_time_analysis.sql
```

I analyzed how sales performance changed over time.

This included:

- Sales by year and month
- Total customers by time period
- Total quantity sold by time period
- Monthly sales trends
- Yearly sales trends

This helped identify growth patterns, seasonality and changes in customer activity.

## 8. Cumulative Analysis

Script:

```text
08_cumulative_analysis.sql
```

I used window functions to calculate cumulative metrics over time.

This included:

- Running total sales
- Moving average price
- Long-term sales growth trends

This analysis helped show how revenue accumulated over time instead of only looking at each period separately.

## 9. Performance Analysis

Script:

```text
09_performance_analysis.sql
```

I analyzed product performance by comparing yearly sales against benchmark values.

This included:

- Current yearly sales
- Average sales per product
- Difference between current sales and average sales
- Previous year sales using `LAG()`
- Difference between current year and previous year sales
- Performance labels such as above average, below average, increase, and decrease

This helped understand whether each product was improving, declining or performing consistently.

## 10. Data Segmentation

Script:

```text
10_data_segmentation.sql
```

I created meaningful segments using SQL `CASE` statements.

### Product Cost Segmentation

Products were grouped into cost ranges:

```text
Below 100
100-500
500-1000
Above 1000
```

### Customer Segmentation

Customers were grouped based on spending behavior and lifespan:

```text
VIP
Regular
New
```

Customer segmentation logic:

- VIP customers have at least 12 months of history and spending above 5,000
- Regular customers have at least 12 months of history and spending of 5,000 or less
- New customers have a lifespan of less than 12 months

This helped convert raw measures into useful business categories.

## 11. Part-to-Whole Analysis

Script:

```text
11_part_to_whole_analysis.sql
```

I analyzed how each product category contributed to total sales.

This included:

- Total sales by category
- Overall sales
- Percentage contribution of each category to total sales

This helped identify which product categories had the largest impact on overall revenue.

## Final Reports

## Customer Report

Script:

```text
12_report_customers.sql
```

Output view:

```text
gold.report_customers
```

The customer report creates a customer-level view that combines customer details, order activity, segmentation and KPIs.

It includes:

- Customer key
- Customer number
- Customer name
- Age
- Age group
- Customer segment
- Last order date
- Recency in months
- Total orders
- Total sales
- Total quantity purchased
- Total products purchased
- Customer lifespan
- Average order value
- Average monthly spend

This report helps answer questions such as:

- Who are the VIP customers?
- Which customers are new or regular?
- Which customers generate the most revenue?
- How recently did each customer place an order?
- What is the average monthly spend per customer?

## Product Report

Script:

```text
13_report_products.sql
```

Output view:

```text
gold.report_products
```

The product report creates a product-level view that combines product details, sales activity, segmentation and KPIs.

It includes:

- Product key
- Product name
- Category
- Subcategory
- Cost
- Last sales date
- Recency in months
- Product performance segment
- Total orders
- Total sales
- Total quantity sold
- Total customers
- Product lifespan
- Average selling price
- Average order revenue
- Average monthly revenue

Product performance segments include:

```text
High Performer
Mid-Range
Low Performer
```

This report helps answer questions such as:

- Which products generate the most revenue?
- Which products are high performers?
- Which products are low performers?
- How recently was each product sold?
- What is the average monthly revenue per product?

## Key Business Questions Answered

This project answers questions such as:

- What is the total revenue generated?
- How many orders, products and customers are in the dataset?
- Which countries have the most customers?
- Which product categories generate the most revenue?
- Which products are the best and worst performers?
- How have sales changed over time?
- What are the monthly and yearly sales trends?
- Which customers generate the highest revenue?
- Which customers are VIP, Regular or New?
- Which products are High, Mid-Range or Low performers?
- What percentage of total sales comes from each category?
- What is the average order value per customer?
- What is the average monthly revenue per product?

## SQL Concepts Used

- SQL Server
- Database creation
- Schema creation
- Table creation
- `BULK INSERT`
- DDL
- DQL
- Joins
- Left joins
- Aggregations
- `GROUP BY`
- `ORDER BY`
- `DISTINCT`
- Subqueries
- Common Table Expressions
- Window functions
- `RANK()`
- `LAG()`
- `SUM() OVER()`
- `AVG() OVER()`
- `CASE` statements
- Date functions
- `DATEDIFF`
- `YEAR`
- `MONTH`
- `DATETRUNC`
- Views
- KPI calculation
- Customer segmentation
- Product segmentation

## Final Output

The final output of this project is two SQL reporting views:

```text
gold.report_customers
gold.report_products
```

These views are ready to be used for business reporting, dashboarding or further SQL analysis.

## Skills Demonstrated

This project demonstrates my ability to:

- Explore database tables and metadata
- Analyze dimensions, dates and measures
- Write SQL queries for business analysis
- Use joins to combine fact and dimension tables
- Apply aggregations for KPI calculation
- Use CTEs and subqueries for structured SQL logic
- Use window functions for ranking, cumulative and performance analysis
- Segment customers and products using SQL
- Create reusable SQL views for reporting
- Build business-ready customer and product reports

