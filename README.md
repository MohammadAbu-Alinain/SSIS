# 🚗 SSIS Project: Car Sales Data Integration

## 📌 Overview
This SSIS (SQL Server Integration Services) project is built to **consolidate**, **transform**, and **store** car sales data coming from **two different flat file sources** into a **relational database** for analysis and reporting.

The ETL (Extract, Transform, Load) process ensures that raw data is unified, cleaned, and aggregated before being inserted into the target destination.

---

## 📊 Data Flow Design

```text
Flat File Source (Cars for sale 1)
                      \
                       \
                        --> [Union All] --> [Derived Column] --> [Aggregate] --> [OLE DB Destination]
                       //
Flat File Source (Cars for sale 2)
```

---

## 🧩 Components Breakdown

### 📄 Flat File Sources (Cars for Sale 1 & 2)
- Reads structured data from two CSV/flat files.
- Each file contains car listings with similar schema.

### 🔀 Union All
- Combines both input sources into a **single unified dataset**.

### 🧪 Derived Column
- Dynamically creates or modifies columns.
- Typical operations include:
  - Calculating new fields (e.g., total price with tax)
  - Formatting or parsing data (e.g., converting strings to dates)
  - Default value assignments

### ➗ Aggregate
- Performs aggregation tasks such as:
  - Counting total number of listings
  - Summing sales amounts
  - Averaging prices by model, make, or other criteria

### 🛢 OLE DB Destination
- Loads the final, cleaned, and aggregated data into a target **SQL Server database**.

---

## 🔧 Requirements

- Microsoft SQL Server Integration Services (SSIS)
- SQL Server or compatible OLE DB database
- Two source files:
  - `Cars_for_sale_1.csv`
  - `Cars_for_sale_2.csv`

---

## 🚀 How to Run

1. Open the project in **SQL Server Data Tools (SSDT)**.
2. Configure the flat file sources:
   - Point to your local copies of `Cars_for_sale_1.csv` and `Cars_for_sale_2.csv`.
3. Set up the OLE DB Destination to connect with your SQL database.
4. Execute the **Data Flow Task** to begin the ETL process.

---

## 💼 Use Cases

- Merging sales data from different dealerships or regions
- Preparing clean, structured datasets for BI/reporting tools
- Performing statistical or business analysis on car sales data

---

## ⚠️ Notes

- Ensure the column names and data types in both flat files are identical for the **Union All** transformation to work correctly.
- Modify **Derived Column** and **Aggregate** components based on your business rules or analysis needs.

---
