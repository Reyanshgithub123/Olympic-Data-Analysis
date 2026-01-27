# Olympic-Data-Analysis
Olympic Data Analytics — End-to-End Azure Data Engineering Project
🧠 Project Overview

This project demonstrates a full end-to-end data engineering pipeline using Microsoft Azure services. It extracts Olympic data from a public API, transforms and processes it using Apache Spark, and loads it into a structured analytics store where SQL queries are used to derive insights and analytics.

The architecture focuses on scalability, reliability, and real-world data workflows — ideal experience for backend, cloud, and data engineering roles.

📌 Key Features

✔ Data Extraction
Fetches Olympic datasets from a REST API on a scheduled basis.

✔ Data Transformation
Processes raw JSON with Apache Spark, cleaning and structuring fields for analytics.

✔ Cloud-Native Workflow
Uses Azure components like Azure Data Factory, Azure Databricks, and Azure Synapse Analytics for orchestration and processing.

✔ SQL Analytics
Loads transformed data to a SQL layer enabling analytics and visualization queries.

✔ Scalable & Reliable Pipeline
Designed to handle growing data volumes and real-time enrichment with monitoring and scheduling.

🛠️ Tech Stack
Layer	Technologies
Extraction	REST API
Processing	Apache Spark, Azure Databricks
Orchestration	Azure Data Factory
Storage	Azure Blob Storage / Data Lake
SQL Analytics	Azure Synapse Analytics
Scheduling	Azure Data Factory Pipelines
Monitoring	Logging & ADF alerts
📁 Project Structure
olympic-data-project/
├── data_extraction/          # API fetch scripts
├── spark_processing/         # Spark notebooks / scripts
├── azure_pipelines/          # Azure Data Factory configurations
├── sql_queries/              # SQL analytics queries
├── docs/                     # Architecture & design docs
├── README.md

🚀 How It Works
1. Data Ingestion

Pull raw Olympic event and athlete data using a Python API client.

Store raw JSON in Azure Blob Storage/Data Lake.

2. Transformation with Spark

Launch an Azure Databricks notebook to:

Load raw data from storage

Clean and normalize fields

Handle schema changes and missing values

Write processed tables back to Delta storage

3. Orchestration

Use Azure Data Factory to:

Trigger pipeline runs (scheduler / dependency)

Chain extraction → transformation → load

4. Analytics

Load processed tables into Azure Synapse Analytics.

Run SQL queries to generate insights (medals by country, performance trends, etc.).

📥 Installation & Setup
Prerequisites

Azure account (with permissions for Data Factory, Databricks, Synapse)

Python (3.7+)

Databricks workspace

REST API access (public Olympic API)

Steps

Clone Repository

git clone https://github.com/your-username/olympic-data-project.git
cd olympic-data-project


Configure Azure Resources

Setup Azure Blob Storage container

Create Azure Data Factory pipeline

Setup Azure Databricks Workspace & cluster

Configure Azure Synapse Analytics SQL pool

Update Config
Edit config.json with your Azure keys & endpoints:

{
  "storage_account": "<your-storage-name>",
  "container": "<container>",
  "api_key": "<optional>",
  "databricks_token": "<token>"
}


Run Pipelines

Trigger ADF pipeline to start extraction

Monitor Databricks jobs

Review loaded tables in Synapse

📊 Sample SQL Query
SELECT Country, COUNT(*) AS MedalCount
FROM olympic_medals
WHERE Year >= 2000
GROUP BY Country
ORDER BY MedalCount DESC;

🧪 Expected Outcomes

Clean, schema-ready Olympic records in data warehouse

Automated daily ingestion of updates

Insights such as medal leaders, athlete trends, country comparisons

Full Azure workflow demonstrating modern data engineering
