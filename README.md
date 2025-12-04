Wealth Analytics Data Platform
A comprehensive Azure Data Factory-based ETL solution for automated ingestion, transformation, and warehousing of wealth management data. This project implements a metadata-driven architecture that processes 12 CSV data sources into a dimensional data warehouse, enabling real-time analytics for advisors, clients, portfolios, and performance metrics.

📊 Project Overview
FinWealth Advisors needed a modern, scalable data platform to:

Automate CSV ingestion from multiple sources

Transform raw data into clean, analytical tables

Enable real-time dashboards and reporting

Scale to handle growth from hundreds to thousands of clients

This solution delivers a zero-manual-intervention ETL pipeline that runs nightly and powers business intelligence tools like Power BI and Tableau.

🏗️ Architecture
text
Blob Storage (CSV Files)
        ↓
Azure Data Factory Pipeline
        ↓
Staging Tables (staging schema)
        ↓
Stored Procedures (Transformation)
        ↓
Data Warehouse (dw schema)
        ↓
Power BI / Tableau / Analytics
Key Components:
Component	Purpose
Azure Data Factory	Orchestrates ETL pipeline with dynamic file processing
Blob Storage	Stores raw CSV files for ingestion
Staging Tables	Temporary storage for raw data validation
DW Schema	Production dimensional and fact tables
Stored Procedures	Data transformation and business logic
Metadata Tables	Drives dynamic pipeline configuration
📁 Data Model
Dimension Tables
DimClient - Client master data (segment, risk profile, country)

DimAdvisor - Advisor details (region, experience, join date)

DimAccount - Account information (type, status, currency)

DimSecurity - Security master (ticker, asset class, sector)

DimDate - Time dimension (year, quarter, month, day, weekday)

Fact Tables
FactPortfolioPerformance - Central fact table with holdings, trades, fees, and performance metrics

Staging Tables
staging.Clients, staging.Accounts, staging.Advisors, ...

All 12 CSV sources loaded into corresponding staging tables
