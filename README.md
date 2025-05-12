Azure Healthcare RCM Project:

This is an end-to-end Data Engineering pipeline project on Healthcare Revenue Cycle Management using Madallion Architecture.

Tech Stack - The Azure Services used in this pipeline includes:

	-For Storage: Azure Data Lake Storage Gen2 (ADLS Gen2)
	-For ETL & Orchestration: Azure Data Factory (ADF), Databricks
	-For Data Processing: PySpark, Delta Lake, Unity Catalog
	-For Security: Azure Key Vault, Linked Services
        - Data Sources: Azure SQL, APIs, JSON, CSV

Pipeline Overview:

	-Landing Zone: Raw CSV/JSON files are ingested
	-Bronze Layer:
		-Ingest data from Azure SQL using ADF (parameterized ETL, incremental/full loads)
		- Store data in Parquet format (partitioned by Year/Month/Day) with Snappy compression
		- Maintain an audit log (file count, records inserted)
		- Ingest NPI, ICD, and CPT data from APIs
	- Silver Layer (Databricks):
		- Data Cleaning & Filtering
		- SCD Type 2 Implementation
		- Common Data Model (CDM) Integration
		- Delta Tables with Unity Catalog
	- Gold Layer (Databricks):
		- Transform data into Fact & Dimension Models with foreign key relationships


Additional Services Includes:
-Databricks Mount for ADLS Access
-Secure Credentials via Key Vault
-Metadata-driven ETL Processing
		
  
This project ensures a scalable, efficient, and secure data pipeline for handling healthcare data.


