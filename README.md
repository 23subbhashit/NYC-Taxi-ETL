# NYC Taxi Trip Analytics ETL Pipeline

## Overview

This project implements a scalable ETL (Extract, Transform, Load) pipeline using PySpark to process New York City Yellow Taxi trip data stored in Parquet format.

The pipeline transforms millions of raw trip records into clean, enriched, and analytics-ready datasets that can be queried efficiently using Spark SQL for business intelligence and operational analysis.

---

## Problem Statement

Transportation companies generate millions of trip records every day containing information such as pickup times, dropoff times, trip distances, fares, passenger counts, and payment details.

Raw operational data cannot be directly used for analytics because:

- Records may contain missing values.
- Invalid trips (zero distance or zero fare) can distort business metrics.
- Important analytical features such as trip duration and average speed are not available.
- Large-scale datasets are difficult to query efficiently without preprocessing.
- Business users need summarized insights rather than individual trip records.

Without a data processing pipeline, analysts and decision-makers cannot accurately answer questions such as:

- What are the busiest pickup hours?
- Which time periods generate the highest revenue?
- How does average trip distance vary throughout the day?
- What are the traffic patterns across different hours?
- How many trips occur during peak demand periods?

---

## Solution

This ETL pipeline addresses these challenges by:

### Extract
- Reading raw taxi trip data from Parquet files using PySpark.

### Transform
- Removing records with missing critical values.
- Filtering invalid trips with zero distance or fare amounts.
- Calculating trip duration from pickup and dropoff timestamps.
- Computing average trip speed.
- Extracting pickup hour for time-based analytics.
- Generating business-friendly analytical features.

### Load
- Persisting the processed dataset into Spark SQL tables for downstream consumption.

---

## Business Value

The processed dataset enables:

- Peak hour demand analysis
- Revenue trend monitoring
- Traffic and congestion analysis
- Operational performance reporting
- Dashboard and BI reporting
- Feature generation for machine learning models

---

## Data Pipeline Flow

Raw Parquet Data
↓
Data Extraction
↓
Data Quality Validation
↓
Feature Engineering
↓
Aggregation & Analytics
↓
Spark SQL Warehouse Table
↓
Business Reporting & Insights

---

## Key Features Generated

| Feature | Description |
|----------|-------------|
| Trip Duration | Time taken to complete a trip |
| Average Speed | Estimated trip speed based on distance and duration |
| Pickup Hour | Hour of the day used for demand analysis |
| Average Fare | Revenue metrics by time period |
| Average Distance | Travel pattern analysis |

---

## Technologies Used

- PySpark
- Spark SQL
- Parquet
- Python
- Google Colab / Apache Spark

---

## Example Analytics

The pipeline can answer business questions such as:

- Which hour has the highest taxi demand?
- What is the average fare during morning and evening rush hours?
- How does trip distance vary across the day?
- Which periods experience the highest congestion based on average speed?

---

## Outcome

The project converts over 3.4 million raw taxi trip records into a clean and queryable analytical dataset, enabling scalable reporting, operational monitoring, and future machine learning use cases.
