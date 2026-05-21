# azure-adf-medallion-project

# Azure Data Engineering Project – Medallion Architecture

## Project Overview

This project demonstrates an end-to-end ETL pipeline using Azure Data Factory (ADF) and Azure Data Lake Storage (ADLS) following the Medallion Architecture approach.

The pipeline processes retail customer and order data through Bronze, Silver, and Gold layers.

---

## Architecture

Bronze Layer → Raw CSV data ingestion
Silver Layer → Cleaned and transformed data
Gold Layer → Aggregated business insights

---

## Technologies Used

* Azure Data Factory (ADF)
* Azure Data Lake Storage Gen2 (ADLS)
* Data Flows
* CSV datasets
* Incremental Load Logic
* Medallion Architecture

---

## Pipeline Features

### Bronze Layer

* Raw customer, order, and store CSV files stored in ADLS

### Silver Layer

* Data cleaning and transformations
* Joins between customers, orders, and stores

### Gold Layer

* Customer-level aggregations
* Total orders per customer
* Total spending per customer

---

## Incremental Load Implementation

Implemented incremental loading using `order_date` watermark filtering.

Example filter logic:

```sql
toDate(order_date) > toDate($last_run_date)
```

---

## Output

Generated aggregated customer summary dataset containing:

* customer_id
* customer_name
* total_orders
* total_spent

---

## Project Screenshots

Screenshots are available in the `/screenshots` folder.

---

## Future Improvements

* Control table for watermark management
* SCD Type 2 implementation
* Power BI dashboard integration
* Azure Synapse Analytics integration

