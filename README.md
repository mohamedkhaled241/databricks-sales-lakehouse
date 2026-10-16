# Databricks Sales Lakehouse

## Project Overview
This project implements a sales data pipeline using Databricks and PySpark. It processes raw sales, customer, product, and location data through the Medallion Architecture to build a structured data warehouse for analytical use cases.

## Architecture
The project follows the Medallion Architecture:

- **Bronze Layer:** Ingests raw CSV source data into Databricks tables.
- **Silver Layer:** Cleans and transforms the data, standardizes data types, handles key inconsistencies, and prepares the datasets for integration.
- **Gold Layer:** Builds analytical fact and dimension tables to support reporting and business analysis.

## Data Sources
The project uses CSV files containing sales, customer, product, and location information.

## Technologies Used
- Databricks
- Apache Spark
- PySpark
- SQL
- Delta Lake
- Git and GitHub
- Medallion Architecture
- Data Warehousing

## Data Warehouse
The Gold layer contains a sales fact table and dimension tables for analytical reporting.

The fact table stores sales measures and transaction dates, while the dimension tables provide descriptive information about customers, products, and locations.

## Data Transformations
The pipeline includes:
- Data type standardization
- Date parsing and validation
- Derived column creation
- Business key standardization
- Joining sales data with customer, product, and location data
- Fact and dimension table preparation

## Repository Structure
- `bike_lakehouse/` — Project notebooks and supporting files
- `sample_data/` — Sample CSV source data, if organized separately

## How to Run
1. Clone or download this repository.
2. Import the notebooks into your Databricks workspace or Git folder.
3. Upload the source CSV files to an accessible Databricks storage location.
4. Update file paths and catalog/schema names to match your environment.
5. Run the notebooks in Bronze, Silver, and Gold order.

## Project Goal
The goal is to demonstrate an end-to-end data engineering workflow, from raw data ingestion to transformation and analytical data modeling, using Databricks and PySpark.
