🚗 SSIS Project: Car Sales Data Integration
Overview
This SSIS (SQL Server Integration Services) project is designed to consolidate and process car sales data from two different flat file sources. The goal is to transform, aggregate, and store the combined data into a relational database (OLE DB Destination) for further analysis and reporting.

📊 Data Flow Overview
Flat File Source (Cars for sale 1)
                    \
                     \
                    [Union All] ----> [Derived Column] ----> [Aggregate] ----> [OLE DB Destination]
                     /
Flat File Source (Cars for sale 2)


Components:
Flat File Source (Cars for sale 1 & 2)

Reads raw data from two separate flat files containing car sales listings.

Union All

Merges both data sources into a single unified stream for processing.

Derived Column

Adds or modifies columns dynamically. Common uses include:

Creating calculated fields

Data formatting (e.g., parsing dates or modifying text)

Setting default values

Aggregate

Performs grouping and aggregation operations such as:

Counting listings

Summing prices or quantities

Calculating averages

OLE DB Destination

Inserts the final transformed data into a SQL Server table or another supported database system.

🔧 Requirements
SQL Server Integration Services (SSIS)

SQL Server or another OLE DB-compatible database

Source flat files: Cars_for_sale_1.csv, Cars_for_sale_2.csv

🚀 How to Run
Open the SSIS solution in SQL Server Data Tools (SSDT).

Configure the flat file connection managers to point to your local CSV files.

Configure the OLE DB Destination to match your database settings.

Execute the Data Flow Task to process and load the data.

Use Cases
Merging datasets from different vendors or branches

Performing ETL operations for reporting systems

Creating business insights from transactional sales data

📌 Notes
Make sure the schema (column names and types) of both flat files match for the Union All to work correctly.

Customize the Derived Column and Aggregate transformations to match your business logic.


