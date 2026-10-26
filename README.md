# Databricks_end_to_end_ecommerce_project

# 🛒 E-Commerce Data Engineering Pipeline Using Databricks

## 📌 Project Overview

This project implements an end-to-end **E-Commerce Data Engineering Pipeline** using Azure Databricks and the Medallion Architecture. It transforms raw e-commerce data into clean, structured, analytics-ready datasets for business intelligence (BI) and sales analysis.

The project uses **Unity Catalog** for centralized data organization and governance, PySpark for data processing, and Delta Lake for storing structured data across Bronze, Silver, and Gold layers.

## 🎯 Project Objectives

- Build an end-to-end ETL pipeline using Databricks.
- Implement the Medallion Architecture: Bronze, Silver, and Gold.
- Create and manage a catalog using Unity Catalog.
- Clean, validate, and transform raw datasets using PySpark and Spark SQL.
- Build fact and dimension tables for analytical reporting.
- Calculate sales metrics and analyze customer and product performance.
- Prepare Gold-layer datasets for BI dashboards and reporting.

## 🏗️ Architecture

The project follows the **Medallion Architecture**:

### 🥉 Bronze Layer — Raw Data Ingestion
- Ingest raw CSV datasets into Databricks.
- Store the data as Delta tables.
- Preserve source data for downstream processing.
- Organize raw tables under the Bronze schema.

### 🥈 Silver Layer — Data Cleaning and Transformation
- Handle missing and inconsistent values.
- Remove duplicate records where appropriate.
- Standardize data types and formats.
- Validate and transform data using PySpark.
- Store cleaned datasets as Delta tables.

### 🥇 Gold Layer — Business-Ready Data
- Create fact and dimension tables.
- Calculate gross sales, discounts, taxes, and net sales.
- Convert sales values into INR for consolidated analysis.
- Prepare structured datasets for BI dashboards and business reporting.

## 🗂️ Unity Catalog Structure

The project creates an `ecommerce` catalog with three schemas.

```text
ecommerce
│
├── bronze
│   ├── brz_order_items
│   ├── brz_brands
│   ├── brz_category
│   ├── brz_products
│   ├── brz_customers
│   └── brz_calendar
│
├── silver
│   ├── slv_order_items
│   ├── slv_brands
│   ├── slv_category
│   ├── slv_products
│   ├── slv_customers
│   └── slv_calendar
│
└── gold
    ├── gld_fact_order_items
    ├── gld_dim_products
    ├── gld_dim_customers
    └── gld_dim_date
```

## 📊 Key Business Metrics

The project produces the following e-commerce performance metrics:

| Metric | Value |
|---|---:|
| Total Sales | $1.81 Billion |
| Total Transactions | 104,756 |
| Total Customers | 88,495 |
| Products Sold | 245,635 |
| Average Transaction Value | $9,896 |
| Unique Products | 48,702 |

*Note: These metrics are based on the project's reported dashboard values.*

## 📈 Gold Fact Table

The final Gold fact table is:

`ecommerce.gold.gld_fact_order_items`

| Attribute | Value |
|---|---|
| Table Type | Fact Table |
| Total Records | 183,378 |
| Total Columns | 19 |
| Gross Sales | `gross_amount` |
| Discount Amount | `discount_amount` |
| Net Sales | `net_amount` |
| INR Sales | `net_amount_inr` |
| Quantity Sold | `quantity` |
| Transaction Identifier | `transaction_id` |

This table supports sales analysis, transaction reporting, and integration with BI tools.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Azure Databricks | Cloud-based data engineering environment |
| Unity Catalog | Data governance and catalog management |
| Apache Spark | Distributed data processing |
| PySpark | Data ingestion, cleaning, and transformation |
| Spark SQL | Data querying and analytical calculations |
| Delta Lake | Reliable storage for structured data |
| Python | Data processing and pipeline development |
| Databricks Volumes | File storage and access for ingestion |

## 🚀 How to Run the Project

1. Create or access an Azure Databricks workspace.
2. Upload the project notebooks to your workspace.
3. Configure Unity Catalog permissions and create the required catalog and schemas.
4. Upload the source CSV files to a Databricks Volume.
5. Update the notebook paths to match your file locations.
6. Run `setup_catalog.ipynb`.
7. Execute the fact and dimension notebooks in Bronze, Silver, and Gold order.
8. Verify the resulting Delta tables in Unity Catalog.
9. Query the Gold tables to analyze sales and prepare data for BI dashboards.

## 💡 Business Value

This project demonstrates how raw e-commerce data can be transformed into reliable analytical datasets. The Gold layer supports business reporting by making sales, customer, product, and transaction information easier to query and analyze.

The pipeline also demonstrates practical data engineering skills, including data lake organization, distributed processing, data quality management, dimensional modeling, and metric generation.

## 👨‍💻 Skills Demonstrated

- End-to-end ETL pipeline development
- Databricks and Unity Catalog
- Medallion Architecture
- PySpark and Spark SQL
- Delta Lake
- Data cleaning and validation
- Fact and dimension modeling
- Sales analytics and business metrics
- BI-ready dataset preparation


Created by Mahesh Karagaonkar
**Project Title:** E-Commerce Data Engineering Pipeline  
**Primary Technologies:** Azure Databricks, PySpark, SQL, Delta Lake  
**Architecture:** Medallion Architecture (Bronze, Silver, Gold)
