# zomato-data-pipeline
Zomato Data Pipeline
Overview

This project implements an end-to-end batch data pipeline for Zomato-style datasets using Python, SQL, Apache Spark, and Hive.
The pipeline follows the Medallion architecture (Bronze–Silver–Gold) to process raw data into analytics-ready datasets.

The goal of this project is to demonstrate core data engineering fundamentals: data ingestion, transformation, data quality validation, and scalable batch processing.

Architecture
The pipeline is structured using the Medallion Architecture:
Bronze Layer: Raw ingested data (CSV files) stored as-is
Silver Layer: Cleaned and standardized datasets
Gold Layer: Aggregated, analytics-ready tables
Each layer is processed incrementally using Spark transformations.

Tech Stack
Programming: Python, SQL
Big Data Processing: Apache Spark, Spark SQL
Data Warehouse: Apache Hive
Workflow Orchestration: Apache Airflow (if applicable)
Storage: Local filesystem / HDFS
Version Control: Git, GitHub
Note: This project does not use cloud services (AWS, GCP, Azure).

Dataset
The dataset simulates Zomato transactional and restaurant data, including:
Orders
Restaurants
Cities
Ratings
Order timestamps and values
Data is stored in CSV format and ingested in batch mode.

Pipeline Flow
Data Ingestion
Raw CSV files are ingested into the Bronze layer.
Schema is applied during ingestion.

Data Cleaning (Silver Layer)
Null handling
Data type casting
Deduplication
Basic validation checks
Data Transformation (Gold Layer)

Aggregations by city and restaurant
Revenue and rating metrics
Analytics-ready tables for reporting

Data Quality Checks
Schema validation
Record count checks
Null value validation
Basic anomaly detection
zomato-data-pipeline/
│
├── data/
│   ├── raw/                # Bronze layer data
│   ├── silver/             # Cleaned data
│   └── gold/               # Aggregated data
│
├── src/
│   ├── ingestion.py
│   ├── data_cleaning.py
│   ├── transformations.py
│   ├── aggregation.py
│   └── utils.py
│
├── sql/
│   └── hive_queries.sql
│
├── airflow/                # Airflow DAGs (if used)
│
├── requirements.txt
└── README.md

End-to-end batch data pipeline for Zomato-style datasets using Python, SQL, Apache Spark, and Hive, organized with the Medallion (Bronze–Silver–Gold) architecture.
