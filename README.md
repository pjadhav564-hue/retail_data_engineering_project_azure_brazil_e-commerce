### retail_data_engineering_project_azure_brazil_e-commerce

End-to-end Retail Data Engineering project using Azure Databricks, PySpark, SQL &amp; Delta Lake. Implements Bronze, Silver &amp; Gold layers, with Silver focused on data cleaning, validation, transformation and quality. Gold delivers business-ready fact and dimension tables for analytics and reporting.

## Project Overview

End-to-end Retail Data Engineering project built using Azure Databricks, PySpark, Delta Lake, and SQL to develop a scalable data pipeline for processing and transforming e-commerce data.

The project follows a Medallion Architecture (Bronze, Silver, and Gold layers). Raw retail data is ingested into the Bronze layer, where source data is stored and organized. The Silver layer performs data cleansing and transformation, including handling null values, removing duplicates, standardizing column names and data formats, validating records, and applying business rules to create reliable and structured datasets.

The Gold layer contains business-ready fact and dimension tables designed for analytics and reporting. Dimension tables such as Customer, Product, Seller, Category, and Date are created based on defined business requirements, while fact tables integrate transactional information such as orders, order items, payments, and reviews.

The solution uses Delta Lake for reliable storage and data management, while PySpark and SQL are used for large-scale data transformation, joins, aggregations, filtering, and data modeling. The final Gold-layer datasets provide a structured foundation for business intelligence, reporting, customer analysis, sales performance, and operational insights.

## Architecture

Source CSV / E-commerce Data
          ↓
     landing_raw
     ├── raw_data
     └── raw_clean
          ↓
       BRONZE
     ├── raw_bronze
     └── clean_bronze
          ↓
       SILVER
     └── clean_silver
          ↓
        GOLD
     Fact & Dimension Tables
          ↓
   Business Analytics / BI

## Medallion Architecture 
azure_b3
│
├── landing_raw
│   └── raw_data
│
├── bronze
│   └── raw_bronze
│
├── silver
│   └── clean_silver
│
└── gold
    └── business_ready
    
## Technologies

- Python
- PySpark
- SQL
- Databricks
- Delta Lake
- Azure
- Git/GitHub

### Data Layers

## 1. Landing Layer

Purpose: Store incoming source data before processing.

landing_raw
└── raw_data
Receives CSV/source files.
Data is kept close to the original source format.
Minimal or no transformation.
Acts as the initial ingestion area.

## 2. Bronze Layer

Purpose: Store raw/ingested data in a structured and managed format.

bronze
└── raw_bronze

Ingest data from the Landing layer.
Preserve source-level information.
Add ingestion metadata where required.
Provides a reliable base for downstream processing.

## 3. Silver Layer

Purpose: Create clean, validated, and standardized data.

silver
└── clean_silver

Typical transformations include:

Remove duplicate records
Handle NULL values
Trim unwanted spaces
Standardize column names
Cast data types
Clean string values
Validate records
Apply business rules
Perform joins between related datasets

This is where your main data cleansing and transformation happens.

## 4. Gold Layer

Purpose: Create business-ready data for analytics and reporting.

gold
└── business_ready

Your Gold layer can contain:

# Gold Model

# Dimensions

dim_customer
dim_product
dim_seller
dim_category
dim_date

# Facts

fact_orders
fact_order_items
fact_payments
etc.

Gold data is optimized for business analysis, dashboards, reporting, and KPIs.


## Gold Model

### Dimensions
- dim_customer
- dim_product
- dim_seller
- dim_category
- dim_date

### Fact
- fact_orders

## Key Transformations

- Data cleansing
- Null handling
- Duplicate removal
- String standardization
- Data type casting
- Joins
- SCD implementation
- Business transformations

## Project Structure
