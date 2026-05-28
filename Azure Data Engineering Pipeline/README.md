# Azure Data Engineering Pipeline for Olympics Data

## Project Overview

This project focuses on building an end-to-end data engineering pipeline on Microsoft Azure using Tokyo Olympics data. The pipeline ingests raw CSV data from GitHub, stores it in Azure Data Lake Storage Gen2, transforms the data using Azure Databricks and PySpark and performs SQL-based analytics using Azure Synapse Analytics.

The project demonstrates how cloud-based data engineering workflows can be used to move, clean, transform and analyze data in a structured and scalable way.

## Tools and Technologies Used

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure Databricks
* PySpark
* Apache Spark
* Azure Synapse Analytics
* SQL
* Python
* GitHub
* CSV Files

## Dataset

The project uses Tokyo Olympics data containing multiple CSV files related to:

* Athletes
* Coaches
* Entries by Gender
* Medals
* Teams

These files were used as the source data for ingestion, transformation and analysis.

Link: https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo

## Project Workflow

### 1. Data Ingestion

Azure Data Factory was used to create data pipelines that copied raw CSV files from GitHub into Azure Data Lake Storage Gen2.

### 2. Data Storage

Azure Data Lake Storage Gen2 was used to store both raw and transformed data. Separate folders were created for raw data and transformed data to keep the data pipeline organized.

### 3. Data Transformation

Azure Databricks was used to process the raw data using PySpark. The transformation step included cleaning and preparing the data before storing it back into the transformed data folder in Azure Data Lake Storage Gen2.

### 4. Data Analysis

Azure Synapse Analytics was used to run SQL queries on the transformed data and generate analytical insights from the Tokyo Olympics dataset.

## Key Learnings

* Built an end-to-end Azure data engineering workflow
* Created data ingestion pipelines using Azure Data Factory
* Stored raw and transformed data using Azure Data Lake Storage Gen2
* Used PySpark in Azure Databricks for data transformation
* Queried transformed data using Azure Synapse Analytics
* Understood how different Azure services work together in a data pipeline

## Project Highlights

* Designed a cloud-based ETL pipeline
* Automated data movement from source to data lake
* Organized data into raw and transformed storage layers
* Applied Spark-based transformations using PySpark
* Performed SQL analytics on processed data
