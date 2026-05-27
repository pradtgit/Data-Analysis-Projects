# Coffee Sales Dashboard | Excel Project

## Dashboard Preview

![Coffee Sales Dashboard](https://github.com/user-attachments/assets/ed64bf99-1ee5-4a5b-9a2a-95ab07ce3078)

## Project Overview

This project is an end-to-end Excel dashboard built to analyze coffee sales performance across customers, countries, coffee types, roast types, package sizes and loyalty card status.

The raw data was cleaned, enriched using lookup formulas, converted into an Excel table, and analyzed through PivotTables, PivotCharts, slicers and a timeline filter. The final output is an interactive Coffee Sales Dashboard that allows users to explore sales trends and customer behavior dynamically.

## Objective

The main objective of this project was to transform raw coffee order data into a clean, interactive dashboard that helps answer business questions such as:

- Which coffee types generate the highest sales?
- Which countries contribute the most revenue?
- Who are the top customers by total sales?
- How do sales change over time?
- How do roast type, package size and loyalty card status affect sales?

## Dataset

The project uses three main datasets:

| Sheet | Description |
|---|---|
| `orders` | Contains order-level transaction data such as order date, customer ID, product ID, quantity and sales |
| `customers` | Contains customer details such as customer name, email, country and loyalty card status |
| `products` | Contains product details such as coffee type, roast type, size, unit price, price per 100g and profit |

## Files Included

| File | Description |
|---|---|
| `Data.xlsx` | Raw dataset containing orders, customers and products |
| `coffeeOrdersProject.xlsx` | Final Excel workbook with cleaned data, PivotTables, PivotCharts, and dashboard |

## Tools Used

- Microsoft Excel
- XLOOKUP
- INDEX MATCH
- IF formulas
- PivotTables
- PivotCharts
- Slicers
- Timeline filter
- Excel table formatting
- Data cleaning and transformation

## Data Preparation Steps

### 1. Customer Data Lookup

Customer details were added to the `orders` sheet using `XLOOKUP`.

Fields added:

- Customer Name
- Email
- Country
- Loyalty Card

### 2. Product Data Lookup

Product details were added using a dynamic `INDEX MATCH` formula.

Fields added:

- Coffee Type
- Roast Type
- Size
- Unit Price

### 3. Sales Calculation

A new `Sales` column was calculated using:

```excel
Sales = Unit Price * Quantity
```

### 4. Coffee and Roast Type Cleaning

Short product codes were converted into readable names.

Examples:

| Original Code | Cleaned Value |
|---|---|
| `Rob` | Robusta |
| `Exc` | Excelsa |
| `Ara` | Arabica |
| `Lib` | Liberica |
| `M` | Medium |
| `L` | Light |
| `D` | Dark |

### 5. Formatting

The dataset was formatted to improve readability:

- Dates were formatted clearly using day, month and year
- Package size was formatted in kilograms
- Unit price and sales were formatted as USD currency
- Duplicate records were checked
- The final range was converted into an Excel table for easier PivotTable updates

## Dashboard Features

The final dashboard includes:

### Total Sales Over Time

A line chart showing sales trends over time, split by coffee type:

- Arabica
- Excelsa
- Liberica
- Robusta

### Sales by Country

A bar chart showing total sales by country:

- United States
- Ireland
- United Kingdom

### Top 5 Customers

A bar chart showing the five highest-value customers based on total sales.

### Interactive Filters

The dashboard includes interactive controls:

- Order Date timeline
- Roast Type slicer
- Size slicer
- Loyalty Card slicer

These filters allow users to analyze sales performance across different time periods and customer or product segments.

## Key Insights

Based on the completed dashboard analysis:

- Total sales across the dataset were approximately **$45,134.26**.
- The **United States** generated the highest sales, with approximately **$35,638.88**.
- **Ireland** generated approximately **$6,696.86**, while the **United Kingdom** generated approximately **$2,798.51**.
- **Excelsa** was the top coffee type by sales, generating approximately **$12,306.44**.
- **Liberica** and **Arabica** also performed strongly, generating approximately **$12,054.08** and **$11,768.49** respectively.
- **Robusta** generated the lowest sales among the four coffee types, with approximately **$9,005.25**.
- Light roast coffee generated the highest sales among roast types.
- The 2.5 kg package size contributed the highest sales compared to smaller package sizes.
- Customers without loyalty cards generated slightly higher total sales than customers with loyalty cards.
- The top customer was **Allis Wilmore**, with approximately **$317.07** in total sales.

## How to Use the Dashboard

1. Open `coffeeOrdersProject.xlsx` in Microsoft Excel.
2. Go to the `Dashboard` sheet.
3. Use the timeline to filter sales by date.
4. Use the slicers to filter by roast type, size and loyalty card status.
5. Review how the charts update dynamically based on the selected filters.

## Project Workflow

```text
Raw Data
   ↓
Data Cleaning and Lookups
   ↓
Sales Calculation
   ↓
Excel Table Creation
   ↓
PivotTables
   ↓
PivotCharts
   ↓
Interactive Dashboard
   ↓
Business Insights
```

## Skills Demonstrated

- Data cleaning in Excel
- Data transformation using lookup formulas
- Dynamic formula building with INDEX MATCH
- Sales and customer analysis
- PivotTable and PivotChart creation
- Dashboard design
- Interactive filtering with slicers and timelines
- Business insight generation
- Data visualization and storytelling

## Conclusion

This project demonstrates how Excel can be used to clean, transform, analyze and visualize business sales data. The final dashboard provides a simple and interactive way to understand coffee sales performance across time, countries, customers and product categories.
