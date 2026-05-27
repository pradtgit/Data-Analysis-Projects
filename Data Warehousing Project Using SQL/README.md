# Data Warehousing Using SQL

## Project Overview

This project focuses on creating a SQL Server data warehouse using raw CRM and ERP data. The data includes customer, product, sales, location and product category information from CSV files. It is first loaded into SQL Server, then cleaned, standardized and organized into a structure that can be used for reporting and analysis.

The project follows the Bronze, Silver and Gold layer approach. The Bronze layer keeps the raw source data, the Silver layer stores the cleaned and transformed data and the Gold layer contains the final Star Schema views for analyzing customers, products and sales.

## Objective

The main objective of this project is to:

- Import raw sales, customer, product and location data from CRM and ERP source systems
- Build a structured SQL Server data warehouse
- Clean, standardize and transform messy source data
- Integrate multiple source files into one analytics-ready model
- Create Gold layer views using a Star Schema
- Perform data quality checks to validate the final warehouse
- Prepare the data for reporting, dashboarding and business intelligence

## Tech Stack

- SQL Server
- T-SQL
- SQL Server Management Studio
- CSV files
- Stored Procedures
- ETL
- Data Warehousing
- Star Schema Modeling
- Data Quality Validation

### CRM Source Files

| File Name | Description |
|---|---|
| `cust_info.csv` | Customer profile information such as customer ID, name, marital status, gender and creation date |
| `prd_info.csv` | Product information such as product ID, product key, product name, cost, product line and product dates |
| `sales_details.csv` | Sales transaction data including order number, product key, customer ID, order dates, sales amount, quantity and price |

### ERP Source Files

| File Name | Description |
|---|---|
| `CUST_AZ12.csv` | Additional customer information such as birthdate and gender |
| `LOC_A101.csv` | Customer location and country information |
| `PX_CAT_G1V2.csv` | Product category, subcategory and maintenance information |

## Dataset Size

| Dataset | Rows | Columns |
|---|---:|---:|
| `cust_info.csv` | 18,494 | 7 |
| `prd_info.csv` | 397 | 7 |
| `sales_details.csv` | 60,398 | 9 |
| `CUST_AZ12.csv` | 18,484 | 3 |
| `LOC_A101.csv` | 18,484 | 2 |
| `PX_CAT_G1V2.csv` | 37 | 4 |

## Data Warehouse Architecture

This project follows a layered data warehouse architecture with three layers.

### Bronze Layer

The Bronze layer stores raw data exactly as it comes from the source CSV files. No major transformation is applied at this stage.

Purpose:

- Store raw CRM and ERP data
- Preserve the original structure of source files
- Create a staging area for further transformation

Bronze tables:

- `bronze.crm_cust_info`
- `bronze.crm_prd_info`
- `bronze.crm_sales_details`
- `bronze.erp_cust_az12`
- `bronze.erp_loc_a101`
- `bronze.erp_px_cat_g1v2`

### Silver Layer

The Silver layer contains cleaned, standardized and transformed data. This layer improves data quality before creating the final analytical model.

Purpose:

- Remove duplicate records
- Trim unwanted spaces
- Standardize gender, marital status, country and product line values
- Handle missing or invalid values
- Convert date fields into proper SQL date formats
- Correct inconsistent sales, quantity and price values

Examples of transformations performed:

- Converted marital status codes such as `M` and `S` into `Married` and `Single`
- Converted gender codes such as `M` and `F` into `Male` and `Female`
- Removed duplicate customer records by keeping the most recent customer record
- Extracted category ID and product key from product codes
- Replaced missing product cost values with `0`
- Standardized product line codes into readable values such as `Mountain`, `Road`, `Touring` and `Other Sales`
- Converted integer date fields into proper SQL date values
- Fixed invalid sales values by recalculating `sales = quantity * price`
- Standardized country codes such as `DE`, `US` and `USA`

Silver tables:

- `silver.crm_cust_info`
- `silver.crm_prd_info`
- `silver.crm_sales_details`
- `silver.erp_cust_az12`
- `silver.erp_loc_a101`
- `silver.erp_px_cat_g1v2`

### Gold Layer

The Gold layer contains the final analytics-ready data model. It is built as a Star Schema using dimension and fact views.

Purpose:

- Create business-friendly tables
- Integrate CRM and ERP data
- Prepare data for reporting and dashboarding
- Support sales, customer and product analysis

Gold views:

- `gold.dim_customers`
- `gold.dim_products`
- `gold.fact_sales`

## Gold Layer Star Schema

The Gold layer follows a Star Schema design.

```text
                 gold.dim_customers
                         |
                         |
gold.dim_products ---- gold.fact_sales
```

### Dimension Tables

#### `gold.dim_customers`

This view combines customer information from CRM and ERP sources.

Key fields:

- `customer_key`
- `customer_id`
- `customer_number`
- `first_name`
- `last_name`
- `country`
- `marital_status`
- `gender`
- `birthdate`
- `create_date`

#### `gold.dim_products`

This view combines product details with product category information.

Key fields:

- `product_key`
- `product_id`
- `product_number`
- `product_name`
- `category_id`
- `category`
- `subcategory`
- `maintenance`
- `cost`
- `product_line`
- `start_date`

Only current product records are included by filtering out historical records where `prd_end_dt` is not null.

### Fact Table

#### `gold.fact_sales`

This view stores sales transaction data and connects to the customer and product dimensions using surrogate keys.

Key fields:

- `order_number`
- `product_key`
- `customer_key`
- `order_date`
- `shipping_date`
- `due_date`
- `sales_amount`
- `quantity`
- `price`

## How to Run the Project

### 1. Create the Database and Schemas

Run:

```sql
init_database.sql
```

This creates the `DataWarehouse` database and the three schemas:

- `bronze`
- `silver`
- `gold`

### 2. Create Bronze Tables

Run:

```sql
ddl_bronze.sql
```

This creates the raw Bronze tables that will receive the CSV data.

### 3. Update CSV File Paths

Before loading the Bronze layer, update the file paths inside `proc_load_bronze.sql` so they match the folder location on your machine.

Example:

```sql
FROM 'C:\sql\dwh_project\datasets\source_crm\cust_info.csv'
```

### 4. Create and Run the Bronze Load Procedure

Run:

```sql
proc_load_bronze.sql
```

Then execute:

```sql
EXEC bronze.load_bronze;
```

This truncates the Bronze tables and loads the raw CSV files into the Bronze layer.

### 5. Create Silver Tables

Run:

```sql
ddl_silver.sql
```

This creates the Silver tables that will store cleaned and standardized data.

### 6. Create and Run the Silver Load Procedure

Run:

```sql
proc_load_silver.sql
```

Then execute:

```sql
EXEC silver.load_silver;
```

This cleans, standardizes and transforms the Bronze data into the Silver layer.

### 7. Run Silver Data Quality Checks

Run:

```sql
quality_checks_silver.sql
```

This validates the cleaned Silver layer data before building the final Gold model.

### 8. Create Gold Views

Run:

```sql
ddl_gold.sql
```

This creates the final Gold layer views:

- `gold.dim_customers`
- `gold.dim_products`
- `gold.fact_sales`

### 9. Run Gold Data Quality Checks

Run:

```sql
quality_checks_gold.sql
```

This validates the final Star Schema and checks relationships between the fact and dimension views.

## Data Quality Checks

The project includes data quality validation for both the Silver and Gold layers.

### Silver Layer Checks

The Silver layer quality checks validate:

- Duplicate or null primary keys
- Unwanted spaces in text fields
- Standardized values for gender, marital status, country and product line
- Invalid or out-of-range dates
- Negative or missing product cost values
- Incorrect sales calculations
- Invalid date relationships, such as order date being after shipping date or due date

### Gold Layer Checks

The Gold layer quality checks validate:

- Uniqueness of surrogate keys in dimension views
- Valid relationships between fact and dimension views
- Referential integrity between `gold.fact_sales`, `gold.dim_customers` and `gold.dim_products`

## Key Features

- Designed and implemented a SQL Server data warehouse from raw CSV sources
- Built Bronze, Silver and Gold layers using a structured ETL process
- Created reusable stored procedures for data loading
- Cleaned and standardized customer, product, sales and location data
- Integrated CRM and ERP datasets into a single analytical model
- Built a Star Schema using fact and dimension views
- Added data quality checks to validate accuracy and consistency
- Prepared the final dataset for analytics, dashboards and reporting

## Skills Demonstrated

- SQL Server
- T-SQL
- ETL Development
- Data Warehousing
- Stored Procedures
- Data Cleaning
- Data Transformation
- Data Modeling
- Star Schema Design
- Data Quality Validation
- Business Intelligence Preparation

## Conclusion

This project shows how raw CRM and ERP data can be transformed into a clean SQL Server data warehouse for analysis. By using Bronze, Silver and Gold layers, the project separates raw ingestion, data cleaning and business modeling into clear stages. The final Gold layer provides a simple Star Schema that can be used for reporting, dashboards and business decision-making.
