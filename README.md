
Retail Performance Intelligence System

SQL-Driven Analytical Reporting & BI Dashboard

1. Executive Summary

This project simulates a retail analytics environment where structured SQL transformations are used to convert raw transactional data into actionable business intelligence.

The objective was to design a repeatable analytical pipeline capable of:

Standardizing inconsistent product attributes

Computing executive KPIs

Performing performance segmentation

Supporting outlet-level profitability decisions

The final output is an interactive Power BI dashboard powered by structured SQL queries.

2. Business Problem

Retail leadership required visibility into:

Revenue distribution by outlet type

Performance by outlet size and location tier

Product segmentation (Fat Content)

Yearly sales trend by establishment year

Relative contribution of each segment to total revenue

The existing raw dataset contained inconsistent categorical labels and unstructured aggregation.

3. Data Engineering Approach
3.1 Data Cleaning & Standardization

Handled inconsistent categorical values:

“LF”, “low fat” → standardized to “Low Fat”

“reg” → standardized to “Regular”

Ensured consistent grouping for accurate aggregation.

3.2 Analytical Modeling

Built grouped aggregations and window functions to compute:

Total Sales

Average Sales

Number of Items

Average Rating

Percentage Contribution by Segment

Example (Percentage Contribution using Window Function):

SELECT 
    Outlet_Size,
    SUM(Total_Sales) AS Total_Sales,
    CAST(
        (SUM(Total_Sales) * 100.0 /
        SUM(SUM(Total_Sales)) OVER())
    AS DECIMAL(10,2)) AS Sales_Percentage
FROM blinkit_data
GROUP BY Outlet_Size;


This approach allows relative performance comparison rather than only absolute totals.

3.3 Trend Analysis with Time Dimension

Computed yearly performance using aggregation:

SELECT 
    Outlet_Establishment_Year,
    SUM(Total_Sales) AS Yearly_Sales
FROM blinkit_data
GROUP BY Outlet_Establishment_Year
ORDER BY Outlet_Establishment_Year;


Identified growth phase and stabilization periods across establishment years.

4. Dashboard Capabilities

The Power BI dashboard provides:

Executive KPI panel

Establishment Year trend analysis

Sales by Outlet Size (percentage contribution)

Outlet Location tier comparison

Product category ranking

Fat Content distribution

Designed for decision-support and management-level review.

5. Key Insights

Large outlets contribute the highest total revenue share.

Sales peaked significantly in 2018, then stabilized.

Product segmentation reveals dominant categories driving revenue.

Certain outlet tiers outperform others consistently.

6. Technical Stack

SQL (Aggregation, Window Functions, Data Cleaning)

Power BI (Interactive Visualization & KPI Modeling)

Excel (Initial Data Source)

GitHub (Version Control & Documentation)

7. What This Project Demonstrates

Structured SQL transformation capability

Understanding of business KPI logic

Ability to compute percentage contributions using window functions

Analytical storytelling from data

End-to-end BI workflow understanding


Dashboard:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/03cdc3d0-f229-477a-b4d8-4c693be37923" />







👤 Author

Rasal Miah
Digital Technology & Management – Big Data Engineering
Aspiring Data Engineer | SQL | Data Modeling | Analytics|BI tools|Python

LinkedIn: www.linkedin.com/in/rasalmiah 

