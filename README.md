
🛒 End-to-End Retail Analytics Pipeline (SQL + Power BI)
📌 Project Summary

Designed and implemented an end-to-end retail analytics system to transform raw grocery sales data into structured, decision-ready insights using SQL and Power BI.

The project demonstrates:

Data cleaning & standardization

Analytical data modeling

KPI computation with SQL

Business-driven dashboard design

Structured reporting pipeline

This project reflects a practical data workflow from raw data ingestion to executive-level reporting.

🎯 Business Objective

Retail management needed visibility into:

Overall sales performance

Outlet-level profitability

Product category distribution

Customer rating patterns

Inventory segmentation (Fat Content, Outlet Type, Size)

The goal was to create a scalable analytical framework to support data-driven decisions.

🏗 Solution Architecture
Raw CSV Data
      ↓
SQL Data Cleaning & Standardization
      ↓
Data Modeling (Aggregations & Views)
      ↓
KPI Computation
      ↓
Power BI Dashboard (Interactive Reporting)

🧹 Data Engineering & SQL Implementation
1️⃣ Data Cleaning

Standardized categorical variables (e.g., "LF", "low fat" → "Low Fat")

Removed inconsistencies in outlet types

Validated missing values

Ensured aggregation integrity

Example transformation:

UPDATE blinkit_data
SET Item_Fat_Content =
    CASE
        WHEN Item_Fat_Content IN ('LF', 'low fat') THEN 'Low Fat'
        WHEN Item_Fat_Content = 'reg' THEN 'Regular'
        ELSE Item_Fat_Content
    END;

2️⃣ KPI Computation

Key KPIs calculated using SQL:

Total Sales

Average Sales

Total Number of Items

Average Customer Rating

Example:

SELECT 
    SUM(Total_Sales) AS Total_Sales,
    AVG(Total_Sales) AS Avg_Sales,
    COUNT(*) AS Total_Items,
    AVG(Rating) AS Avg_Rating
FROM blinkit_data;

3️⃣ Analytical Segmentation

Advanced SQL analysis performed for:

Sales by Outlet Tier (Tier 1, 2, 3)

Sales Contribution by Outlet Size

Fat Content Sales Distribution

Outlet Type Comparison

Establishment Year Trend

Example aggregation:

SELECT Outlet_Size,
       SUM(Total_Sales) AS Sales
FROM blinkit_data
GROUP BY Outlet_Size
ORDER BY Sales DESC;

📊 Dashboard Features (Power BI)

The interactive dashboard includes:

KPI cards (Total Sales, Avg Sales, Items, Rating)

Outlet establishment trend analysis

Category-level sales distribution

Fat content performance comparison

Outlet size & location contribution analysis

Dynamic filtering by outlet type and size

The dashboard allows management to quickly identify performance drivers and underperforming segments.

Dashboard:
<img width="1346" height="775" alt="Screenshot 2026-02-13 080245" src="https://github.com/user-attachments/assets/b65f47d8-82f5-4289-b133-b1d7ecef0f02" />




📈 Key Insights

Large outlets contribute the highest overall revenue share.

Low Fat product category generates strong sales volume.

Certain outlet tiers consistently outperform across multiple KPIs.

Sales trends correlate with establishment year maturity.

🛠 Tech Stack

SQL (Data Cleaning, Aggregation, Modeling)

Power BI (Visualization & Interactive Reporting)

CSV Data Processing

Data Modeling Concepts

Repository Structure
/data        → Raw dataset (if publicly shareable)
/sql         → Cleaning & analytical SQL queries
/dashboard   → Dashboard preview images
/docs        → Architecture & assumptions
README.md    → Project documentation




👤 Author

Rasal Miah
Digital Technology & Management – Big Data Engineering
Aspiring Data Engineer | SQL | Data Modeling | Analytics|BI tools|Python

LinkedIn: www.linkedin.com/in/rasalmiah 

