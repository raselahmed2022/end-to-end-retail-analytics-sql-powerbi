**# end-to-end-retail-analytics-sql-powerbi
Designed a structured data pipeline to analyze retail sales performance across outlet types, item categories, and establishment years.
**# Retail Sales Data Pipeline & BI System (SQL + Power BI)

An end-to-end analytics project that demonstrates how raw retail data can be cleaned, transformed, modeled, and visualized for decision-making.  
**Focus:** SQL transformation + data modeling + KPI reporting in Power BI.

##  Project Overview
This project analyzes retail sales performance across outlets, item categories, outlet sizes, and establishment years.  
Key KPIs and dimensions are visualized in a Power BI dashboard.

## Key KPIs (Dashboard)
From the dashboard view:
- **Total Sales:** ~1.2M  
- **Avg Sales:** ~141  
- **Avg Rating:** ~3.9  
- **No. of Items:** ~9K  

Additional breakdowns include:
- Fat content segmentation (Low Fat vs Regular)
- Outlet tiers and location distribution (Tier 1/2/3)
- Outlet size (Small/Medium/High)
- Outlet type comparison (e.g., Supermarket Type1/2/3, Grocery Store)
- Establishment-year trend (2012–2022)

> Screenshot reference: see `powerbi/dashboard_preview.pdf` or `docs/dashboard_screenshots/`.

## 🧱 Data Engineering Approach (What I Did)
1. **Data Cleaning & Standardization (SQL)**
   - handled missing values and inconsistent categories
   - standardized outlet/item labels
   - validated totals and duplicates

2. **Data Modeling**
   - created a structured model for analysis (fact + dimensions)
   - built reusable SQL views for KPIs and slice-and-dice

3. **Analytics Layer**
   - KPI queries for sales, items, ratings
   - segmented performance by outlet type, size, and location

4. **BI Layer (Power BI)**
   - interactive dashboard for filtering by outlet location/size/type
   - KPI cards + category and trend charts

## 🧠 Architecture
**Raw Data → SQL Cleaning/Transforms → Analytical Model (Views) → Power BI Dashboard**



## 🛠 Tech Stack
- **SQL:** cleaning, transformations, KPI queries, modeling views  
- **Power BI:** semantic model, measures, interactive dashboard  
- **Excel:** quick validation/sanity checks  
- **Git/GitHub:** version control and documentation  

## 📁 Repository Guide
- `sql/` – scripts for schema, transformations, model views, KPI queries  
- `powerbi/` – dashboard preview + Power BI notes  
- `docs/` – data dictionary, assumptions, architecture diagram  
- `data/` – placeholder for raw/processed (not shared publicly if licensed)

## 🚀 How to Run (Local)
1. Create a database (PostgreSQL / MySQL / SQL Server—adapt scripts accordingly)
2. Run:
   - `sql/01_create_schema.sql`
   - `sql/03_clean_transform.sql`
   - `sql/04_data_model_views.sql`
   - `sql/05_kpi_queries.sql`
3. Open Power BI and connect to the modeled tables/views.

## 📌 Notes
- If the original dataset or PBIX is not shareable (licensing/privacy), this repo still documents the full approach, queries, and model structure.
- I can provide a sample dataset structure (`docs/data_dictionary.md`) to reproduce the pipeline with any similar retail dataset.

## 👤 Author
**Rasal Miah**  
Big Data Engineering Student | SQL • Data Modeling • Power BI•Python
LinkedIn: www.linkedin.com/in/rasalmiah 

