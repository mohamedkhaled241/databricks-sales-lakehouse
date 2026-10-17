# Databricks Sales Lakehouse

## Project Overview
This project implements a sales data pipeline using Databricks and PySpark. It processes raw sales, customer, product, and location data through the Medallion Architecture to build a structured data warehouse for analytical use cases.

## Architecture
The project follows the Medallion Architecture:

- **Bronze Layer:** Ingests raw CSV source data into Databricks tables.
- **Silver Layer:** Cleans and transforms the data, standardizes data types, handles key inconsistencies, and prepares the datasets for integration.
- **Gold Layer:** Builds analytical fact and dimension tables to support reporting and business analysis.

- ## Architecture Diagram

![Databricks Sales Lakehouse Architecture](architecture.png)

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

The Gold layer contains a sales fact table and dimension tables for customers, products, and locations.

### Fact Table Grain

The sales fact table is designed at the **order-line level**, where each row represents a specific product within an order.

An order containing multiple products is represented by multiple rows, one for each product line. This grain supports detailed sales analysis by order, product, customer, and location.

The fact table stores measures such as sales amount and quantity, along with transaction dates and keys used to connect to the dimension tables.

### Dimension Tables

The dimension tables provide descriptive attributes for customers, products, and locations, enabling multidimensional sales analysis.


## Data Transformations
The pipeline includes:
- Data type standardization
- Date parsing and validation
- Derived column creation
- Business key standardization
- Joining sales data with customer, product, and location data
- Fact and dimension table preparation

## Repository Structure

- `bike_lakehouse/` — Main project directory
- `crm_cust_info/` — Customer data processing notebooks
- `crm_prd_info/` — Product data processing notebooks
- `crm_sales_info/` — Sales data processing notebooks
- `rep_loc_info/` — Location data processing notebooks
- `Gold_fact_sales.csv` — Exported Gold fact table
- `sales_details.csv` — Sales source data
- `cust_info.csv` — Customer source data
- `prd_info.csv` — Product source data
- `LOC_A101.csv` — Location source data


## How to Run
1. Clone or download this repository.
2. Import the notebooks into your Databricks workspace or Git folder.
3. Upload the source CSV files to an accessible Databricks storage location.
4. Update file paths and catalog/schema names to match your environment.
5. Run the notebooks in Bronze, Silver, and Gold order.

## Project Goal
The goal is to demonstrate an end-to-end data engineering workflow, from raw data ingestion to transformation and analytical data modeling, using Databricks and PySpark.
