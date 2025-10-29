# Data-Warehouse-with-PySpark-DBT


This repository contains the source code for a complete, end-to-end data engineering project that combines the power of PySpark for data processing and dbt (data build tool) for transformation and modeling.

The project builds a full Dimensional Data Model from scratch. It handles everything from raw data ingestion (both batch and streaming) to advanced, analytics-ready tables. It serves as a practical guide for integrating PySpark's processing capabilities with dbt's transformation, testing, and documentation framework.

Key Concepts & Project Recall (What I Learned)
This project is structured around a modern data stack, covering the following key areas:

PySpark (The "Engine"):

Basics: You used PySpark DataFrames to read, write, and manipulate large-scale data.

Incremental Ingestion: You built a Bronze layer pipeline to efficiently ingest only new or changed data, avoiding full table scans.

Spark Streaming: You used Structured Streaming to create a pipeline that can process data in near real-time as it arrives, not just in batches.

dbt (The "Transformer"):

dbt Models: You built the Silver and Gold layers using dbt. You defined your transformations as SQL SELECT statements in .sql files, and dbt managed the dependencies and materialization (as tables or views) for you.

dbt Snapshots: You used the dbt snapshot command to automatically implement a Slowly Changing Dimension (SCD) Type 2.

Data Warehousing (The "Result"):

Dimensional Modeling: The final output of the Gold layer is a Star Schema. You built:

Dimension Tables: (e.g., dim_customers, dim_products) which hold the descriptive "who, what, where" attributes.

Fact Tables: (e.g., fct_orders) which hold the numerical measures and foreign keys to the dimensions.

Slowly Changing Dimensions (SCD): You specifically used dbt Snapshots to automatically capture history (SCD Type 2). This creates a table that tracks all historical versions of a record (e.g., a customer's address changes), keeping the dbt_valid_from and dbt_valid_to columns up to date.
