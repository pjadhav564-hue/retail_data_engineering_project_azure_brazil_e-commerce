# retail_data_engineering_project_azure_brazil_e-commerce

## Name : Pratik Jadhav

## Course: Data Engineering

## Subject: Brazilian E-commerce Data Engineering

## Tool Used: Azure Databricks, PySpark, SQL, Delta Lake, Azure Data Lake Storage, GitHub


## Introduction
This project is an end-to-end Brazilian E-commerce Data Engineering solution built using Azure Databricks, PySpark, SQL, and Delta Lake.
It processes raw e-commerce data through Bronze, Silver, and Gold layers, where data is cleaned, transformed, and prepared for business analysis.
The final Gold layer provides business-ready dimension and fact tables that can be used for reporting, analytics, and decision-making.

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

## Data Layers

### 1. Landing Layer

Purpose: Store incoming source data before processing.

landing_raw
└── raw_data
Receives CSV/source files.
Data is kept close to the original source format.
Minimal or no transformation.
Acts as the initial ingestion area.

### 2. Bronze Layer

Purpose: Store raw/ingested data in a structured and managed format.

bronze
└── raw_bronze

Ingest data from the Landing layer.
Preserve source-level information.
Add ingestion metadata where required.
Provides a reliable base for downstream processing.

### 3. Silver Layer

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

### 4. Gold Layer

Purpose: Create business-ready data for analytics and reporting.

gold
└── business_ready


## Gold Model

### Dimensions

dim_customer
dim_product
dim_seller
dim_category
dim_date

### Facts

fact_orders
fact_order_items
fact_payments
etc.

Gold data is optimized for business analysis, dashboards, reporting, and KPIs.


## Key Transformations

- Data cleaning
- Null handling
- Duplicate removal
- String standardization
- Data type casting
- Joins
- SCD1 and SCD2 implementation
- Business transformations

## Project Structure

retail-data-engineering-project/
│
├── README.md
├── .gitignore
│
├── notebooks/
│   │
│   ├── bronze/
│   │   └── bronze_ingestion.py
│   │
│   ├── silver/
│   │   ├── silver_customers.py
│   │   ├── silver_orders.py
│   │   ├── silver_order_items.py
│   │   ├── silver_payments.py
│   │   ├── silver_products.py
│   │   ├── silver_sellers.py
│   │   ├── silver_reviews.py
│   │   ├── silver_geolocation.py
│   │   └── silver_category_translation.py
│   │
│   └── gold/
│       │
│       ├── dimensions/
│       │   ├── dim_customers.py
│       │   ├── dim_product.py
│       │   ├── dim_seller.py
│       │   ├── dim_category.py
│       │   └── dim_date.py
│       │
│       └── facts/
│           └── fact_orders.py
│
├── src/
│   └── functions.py
│
├── sql/
│   └── business_queries.sql
│
└── docs/
    └── architecture.png


## Layer Responsibilities

### Bronze Layer

- Raw data ingestion
- Source data preservation
- Ingestion metadata

### Silver Layer

- Data cleaning and transformation
- Null and duplicate handling
- Schema and column standardization
- Data type conversion
- String and whitespace cleansing
- Data validation and filtering
- Joins and data enrichment
- silver_geolocation
- silver_category_translation

## Gold Layer

### 1. Dimension Tables

Read and prepare dim_customers
Read and prepare dim_product
Read and prepare dim_seller
Read and prepare dim_category
Create dim_date as a derived/calculated date dimension

### 2. Fact Table

Create fact_orders
Integrate required dimension and Silver-layer data
Generate business-ready order-level analytical data

## SCD Implementation

SCD Type 1: Applied where historical changes do not need to be maintained.
SCD Type 2: Applied where historical changes need to be tracked using effective dates/versioning.

The Gold layer provides business-ready dimensional and fact data for analytics, reporting, and decision-making.


## Screenshots

## Azure Databricks Catalog
<img width="1583" height="527" alt="image" src="https://github.com/user-attachments/assets/3b217027-a598-4f42-a35f-ab4984f47961" />

## BRONZE LAYER – RAW INGESTION 
<img width="1346" height="683" alt="image" src="https://github.com/user-attachments/assets/9aea5a8f-433e-46ce-9210-60f3861cf2ef" />
<img width="1403" height="591" alt="image" src="https://github.com/user-attachments/assets/21682b5e-2d5b-4ae3-90c8-91c3623d8285" />

## SILVER LAYER - data cleaning and validation 
<img width="1413" height="573" alt="image" src="https://github.com/user-attachments/assets/3bc9f7e8-b643-4b6d-a150-ae2f1b37ba4d" />



## GOLD LAYER - business ready
<img width="1477" height="700" alt="image" src="https://github.com/user-attachments/assets/45c497f8-05d1-4740-b763-b3517d92e06b" />





