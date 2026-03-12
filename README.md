# End-to-End-Data-Engineering-Project-using-Databricks-Free-Edition-I-FMCG-Domain---using-AWS

FMCG Sales Data Pipeline using Databricks (Free Edition) & AWS S3

📌 Project Overview

This project demonstrates the design and implementation of a production-grade data engineering pipeline using Databricks Lakehouse architecture and AWS S3.

The objective is to transform raw FMCG sales data into business-ready analytical datasets using Medallion Architecture (Bronze → Silver → Gold).

The pipeline simulates how modern organizations build scalable data platforms capable of ingesting raw data, cleaning it, enriching it, and generating analytical insights for business stakeholders.

This project focuses on building an end-to-end ELT pipeline using modern data engineering tools such as:

Databricks Lakehouse

Apache Spark / PySpark

Delta Lake

AWS S3

Auto Loader

Spark Structured Streaming

Databricks Workflows

Unity Catalog

The architecture mirrors real-world enterprise data pipelines used in retail and FMCG companies.

🧠 Business Problem

FMCG companies generate massive volumes of sales data from:

Retail stores

E-commerce platforms

Distribution channels

Inventory systems

However, raw data often contains:

inconsistent formats

missing values

duplicate records

delayed ingestion

Without a structured data pipeline, extracting insights such as:

Product performance

Regional sales trends

Inventory optimization

Customer demand patterns

becomes extremely difficult.

This project solves the problem by building a scalable lakehouse data pipeline.

🏗 Architecture Overview

The pipeline follows the Medallion Architecture pattern, widely used in modern data engineering.

Layers
Layer	Description
Bronze Layer	Raw data ingestion from source systems
Silver Layer	Cleaned, validated, and structured datasets
Gold Layer	Aggregated business-level analytics tables

This layered architecture ensures:

Data reliability

Scalability

Data governance

High performance analytics

🛠 Tech Stack
Category	Technologies
Programming	Python, SQL
Data Processing	PySpark, Spark Structured Streaming
Data Platform	Databricks
Storage	AWS S3
Data Lake Format	Delta Lake
Ingestion	Databricks Auto Loader
Orchestration	Databricks Workflows
Governance	Unity Catalog
Version Control	Git & GitHub
📂 Project Structure
End-to-End-Data-Engineering-FMCG
│
├── data
│   ├── raw
│   ├── processed
│
├── notebooks
│   ├── 01_bronze_ingestion
│   ├── 02_silver_transformation
│   ├── 03_gold_aggregation
│
├── workflows
│   ├── pipeline_orchestration
│
├── images
│   ├── architecture.png
│   ├── bronze_layer.png
│   ├── silver_layer.png
│   ├── gold_layer.png
│
├── README.md
⚙️ Data Pipeline Workflow

The pipeline processes FMCG sales data in three major stages.

🥉 Bronze Layer – Raw Data Ingestion

The Bronze layer stores raw ingested data exactly as it arrives from source systems.

Key Features

Incremental ingestion using Databricks Auto Loader

Real-time ingestion with Spark Structured Streaming

Data stored in Delta Lake format

Raw data preserved for audit and lineage

Example Workflow

Source CSV/JSON files land in AWS S3

Auto Loader detects new files

Streaming ingestion loads data into Bronze Delta Tables

Example PySpark logic:

df = spark.readStream.format("cloudFiles") \
.option("cloudFiles.format", "csv") \
.load("s3://fmcg-raw-data")

df.writeStream.format("delta") \
.outputMode("append") \
.option("checkpointLocation", "/checkpoint/bronze") \
.table("bronze_sales")
🥈 Silver Layer – Data Cleaning & Transformation

The Silver layer transforms raw data into structured and reliable datasets.

Transformations Performed

Removing duplicates

Handling null values

Data type standardization

Data validation

Schema enforcement

Example Transformations
silver_df = bronze_df \
.dropDuplicates() \
.filter(col("sales_amount").isNotNull()) \
.withColumn("sale_date", to_date("sale_timestamp"))
Output

Cleaned datasets ready for analytics.

Examples:

Clean sales dataset

Standardized product dataset

Structured customer dataset

🥇 Gold Layer – Business-Level Aggregations

The Gold layer provides analytics-ready datasets for business intelligence tools.

Example Analytics Tables

Regional sales performance

Product category revenue

Monthly sales trends

Top performing SKUs

Example aggregation:

gold_sales = silver_df.groupBy("region","product_category") \
.agg(sum("sales_amount").alias("total_sales"))

These tables can directly feed:

Power BI

Tableau

Machine Learning models

🔄 Pipeline Orchestration

The entire pipeline is automated using Databricks Workflows.

Workflow steps:

1️⃣ Bronze ingestion
2️⃣ Silver transformation
3️⃣ Gold aggregation
4️⃣ Data validation

This ensures:

Scheduled pipeline execution

Failure monitoring

Dependency management

🔐 Data Governance with Unity Catalog

Unity Catalog is used for:

Data lineage tracking

Access control

Metadata management

Benefits:

Secure data access

Centralized governance

Enterprise-level compliance

📊 Example Business Insights

Using the Gold datasets, FMCG companies can answer questions such as:

Which product categories generate the highest revenue?

Which regions show the fastest growth?

What are the top-selling SKUs?

How does monthly demand fluctuate?

These insights enable:

smarter inventory management

demand forecasting

targeted marketing strategies

📸 Project Screenshots
Databricks Workspace

Bronze Table Example

Silver Cleaned Data

Gold Analytics Table

🚀 Key Data Engineering Concepts Demonstrated

This project demonstrates practical implementation of:

Medallion Architecture

Real-time data ingestion

Delta Lake architecture

Streaming pipelines

ELT pipeline design

Data lakehouse architecture

Pipeline orchestration

Data governance

📈 Skills Demonstrated

This project highlights my expertise in:

Data Engineering

Distributed Data Processing

Lakehouse Architecture

Cloud Data Platforms

Real-time Data Pipelines

Data Governance

These are core skills required for roles such as:

Data Engineer

Analytics Engineer

Cloud Data Engineer

Big Data Engineer

Your resume also highlights similar skills in Databricks, PySpark, Delta Lake, and AWS pipelines 

Gaurav_Singh_DataScience_ATS_Re…

, making this project a strong portfolio example.

🔮 Future Improvements

Possible enhancements to this project:

Integrate Apache Airflow for orchestration

Implement data quality testing (Great Expectations)

Add CI/CD pipeline

Integrate dbt for transformations

Build Power BI dashboard

👨‍💻 Author

Gaurav Singh

📧 gauravbisht2803@gmail.com

🔗 LinkedIn: https://linkedin.com/in/contact-gauravsingh

💻 GitHub: https://github.com/gaurav280303

MBA (AI & Data Science) | Data Engineering & Analytics Enthusiast
