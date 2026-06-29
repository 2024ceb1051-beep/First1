# House Market Analysis Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/ba4c85b6-8f97-4871-8e80-826ed0157218/d5c10ccbb13fe5c1fe20?experience=power-bi

## Problem Statement

This dashboard helps real estate agencies, property investors, and business analysts understand the performance of the housing market across different regions, cities, and property types. It provides valuable insights into property sales, market trends, pricing, and housing characteristics, enabling stakeholders to evaluate the overall performance of the real estate market and identify potential investment opportunities.

The dashboard combines multiple housing market indicators such as total sales, sales growth, property prices, average price per square meter, house types, and regional performance into a single interactive report. Using dynamic slicers and visualizations, users can analyze the housing market from different perspectives and compare performance across regions, cities, and property categories.

By monitoring sales trends, price changes, and regional variations, businesses can make informed decisions regarding investments, pricing strategies, and future developments. The dashboard also helps identify high-performing regions, profitable house categories, and recent market movements, making it a valuable analytical tool for decision-makers.

---

## Steps Followed

* Step 1 : Load data into Power BI Desktop, dataset is a CSV file.

* Step 2 : Open Power Query Editor and inspect the dataset for data quality by verifying column names, data types, and overall data consistency before building the report.

* Step 3 : It was observed that the dataset contains information related to property sales including purchase date, house type, sales type, purchase price, property size, square meter price, address, city, region, mortgage rates, inflation rates, and bond yields.

* Step 4 : Required data type conversions were performed to ensure numerical fields, date fields, and categorical columns were properly recognized by Power BI.

* Step 5 : The dataset was cleaned by removing unnecessary inconsistencies and preparing the data for analysis before loading it into the data model.

* Step 6 : After completing the transformations, the cleaned dataset was loaded into Power BI Desktop.

* Step 7 : A report theme was selected under the View tab to maintain a consistent visual appearance throughout the dashboard.

* Step 8 : Appropriate relationships between tables were verified within the data model to ensure accurate calculations and filtering across visuals.

* Step 9 : Multiple DAX measures were created to calculate important business KPIs including Last 12 Months Sales, Total YTD Sales, Sales Growth, Average Price per Square Meter, Median Sales Price Change, and Units Sold.

* Step 10 : Multiple KPI card visuals were added to display important business metrics such as:

  (a) Last 12 Months Sales

  (b) Total YTD Sales

  (c) Units Sold in Latest Quarter

  (d) Average Price per Square Meter

  (e) Median Sales Price Change

* Step 11 : Multiple slicers were added to provide interactive filtering across the report.

The slicers include:

(a) Region

(b) Area

(c) City

(d) House Type

(e) Sales Type

These slicers allow users to dynamically analyze housing market performance for different locations and property categories.

* Step 12 : Various visualizations were created to analyze different business perspectives including:

  • Clustered Column Charts

  • Clustered Bar Charts

  • Line Charts

  • Scatter Charts

  • Donut Charts

  • Funnel Charts

  • KPI Cards

  • Tables

  • Key Influencers Visual

These visuals help users identify pricing trends, regional performance, house type distribution, and sales growth patterns.

* Step 13 : Interactive filters and cross-highlighting were enabled between visuals, allowing users to drill into specific regions, cities, and house categories.

* Step 14 : Separate report pages were designed to provide different analytical perspectives of the housing market:

  • House Market Overview

  • Sales Performance

  • House Type Analysis

Each page focuses on a different business objective while maintaining consistent navigation and user experience.

* Step 15 : Business KPIs were calculated using DAX measures to monitor market performance, identify regional trends, compare property types, and evaluate yearly sales performance.

* Step 16 : Dynamic visual interactions were configured so that selecting any chart or slicer automatically filters all related visuals across the report.

* Step 17 : Appropriate formatting, titles, legends, labels, tooltips, and color themes were applied to improve dashboard readability and user experience.

* Step 18 : The completed report was published to Power BI Service, allowing users to securely access and interact with the dashboard online.
* Step 19 : Several DAX measures were created to calculate key business metrics used throughout the dashboard.

Following DAX expressions were written for the same,

### Last 12 Months Sales

```DAX
Last 12 Months Sales =
CALCULATE(
    SUM(Housing[purchase_price]),
    DATESINPERIOD(
        Housing[date],
        MAX(Housing[date]),
        -12,
        MONTH
    )
)
```

A KPI card visual was used to represent the total housing sales recorded during the last twelve months.

---

### Units Sold In Latest Year & Quarter

```DAX
Units Sold In Latest Year & Quarter =
CALCULATE(
    DISTINCTCOUNT(Housing[house_id]),
    YEAR(Housing[date]) = YEAR(MAX(Housing[date])) &&
    QUARTER(Housing[date]) = QUARTER(MAX(Housing[date]))
)
```

A KPI card visual was used to display the total number of properties sold during the latest available quarter.

---

### YOY Sales Growth

A DAX measure was created to calculate Year-over-Year Sales Growth, enabling users to compare current sales performance with the previous year's sales and evaluate market growth over time.

---

### Total YTD Sales

A DAX measure was created to calculate cumulative Year-to-Date housing sales, providing a quick overview of current year market performance.

---

### Median Sales Price Change

A DAX measure was created to determine the percentage change in median property prices, allowing users to analyze pricing trends across different regions and property categories.

---

### Average Price SQM

A DAX measure was created to calculate the average selling price per square meter, making it easier to compare housing prices across cities and regions.

---

### Sales By Region

A DAX measure was created to evaluate regional sales contribution and compare the overall market performance between different geographical locations.

---

### Offer to SQM Ratio

A DAX measure was created to analyze the relationship between property pricing and available living area, providing additional insights into property valuation.

---

* Step 20 : Various report pages were designed to provide comprehensive analysis of the housing market.

The report contains three interactive dashboard pages:

(a) House Market Overview

(b) Sales Performance

(c) House Type Analysis

Each report page provides a different business perspective while allowing users to interact using common slicers and filters.

---

* Step 21 : After completing the dashboard development and validation, the report was published to Power BI Service for online access and sharing.

# Snapshot of Dashboard (Power BI Service)

![Power BI Service Dashboard](https://github.com/user-attachments/assets/6c9d8677-cc69-4575-a396-19e30c6449d0)

---

# Report Snapshot (Power BI Desktop)

### House Market Overview

![Dashboard 1](https://private-user-images.githubusercontent.com/296665673/614401376-b3747453-1019-42b9-92ff-eff4db57dd54.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODI3MTkxNTgsIm5iZiI6MTc4MjcxODg1OCwicGF0aCI6Ii8yOTY2NjU2NzMvNjE0NDAxMzc2LWIzNzQ3NDUzLTEwMTktNDJiOS05MmZmLWVmZjRkYjU3ZGQ1NC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNjI5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDYyOVQwNzQwNThaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0zNzQwNzMzNzMzMDBhM2EwNmM1YTk2OGVkNzI0NmJlYWQ1OGNhNjUzZTAyMDM2YzFmMDg2YmU1OGZkY2Y5N2RjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZwbmcifQ.Cma1DIT3h5U2RiCfuRQOz6Yi68-iPLOOgMQjD7z1Id8)

---

### Sales Performance

![Dashboard 2](https://private-user-images.githubusercontent.com/296665673/614434291-abab1f68-6bcb-491b-b0dd-ce2aad90da5b.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODI3MTk2MTgsIm5iZiI6MTc4MjcxOTMxOCwicGF0aCI6Ii8yOTY2NjU2NzMvNjE0NDM0MjkxLWFiYWIxZjY4LTZiY2ItNDkxYi1iMGRkLWNlMmFhZDkwZGE1Yi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNjI5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDYyOVQwNzQ4MzhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yNjBjMjI0MzBmMWZhZGE2MTk2NmNhMzIxMzVjNDhjMDJlZjk5NmQ3OGZiNTA3YWM5NDU0OWY0MWVjZTZlNDljJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZwbmcifQ.XfuE1fxaXiks2q4sSFUL2rZiwxSkhd4aH4D3an29riY)

---

### House Type Analysis

![Dashboard 3](https://private-user-images.githubusercontent.com/296665673/614435644-9ee1f65e-888b-43bc-b721-f00b004ac9fc.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3ODI3MTk3NjgsIm5iZiI6MTc4MjcxOTQ2OCwicGF0aCI6Ii8yOTY2NjU2NzMvNjE0NDM1NjQ0LTllZTFmNjVlLTg4OGItNDNiYy1iNzIxLWYwMGIwMDRhYzlmYy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNjI5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDYyOVQwNzUxMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02Y2Q5NzhiMDg5YjI5OGQ0ZDY0NGMxNzU5ODFkMzg5NWIyMGIzN2FjNmVkMGVkNzQ2ZTQwODQ5MjJkOGQ5ZWFhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZwbmcifQ.Kkd4PP8yYYDddkouUSa_LaUxKJEVSgbq0OIffmjQulw)
# Insights

A three-page interactive report was created on Power BI Desktop and was later published to Power BI Service.

Following inferences can be drawn from the dashboard;

---

### [1] Overall Housing Market Performance

* Last 12 Months Sales = **13bn**

* Total YTD Sales = **9bn**

* Units Sold in Latest Quarter = **77**

* Median Sales Price Change = **3.85%**

* Average Price per SQM = **25K**

These KPIs provide a quick overview of the current housing market performance and automatically update whenever different filters or slicers are applied.

---

### [2] Regional Analysis

* Zealand contributes the highest average property price per square meter among all regions.

* Southern Denmark maintains a comparatively stable housing market with consistent sales performance.

* Central Jutland records strong sales activity across multiple property categories.

* North Jutland contributes a relatively smaller share of total market sales.

The regional comparison helps identify high-performing markets and potential investment locations.

---

### [3] Sales Performance

* Sales fluctuate across different quarters, indicating seasonal variations in housing demand.

* The latest twelve months generated over **13 Billion** in total housing sales.

* Year-to-Date sales have already crossed **9 Billion**, indicating continued market growth.

* Median housing prices show a positive growth trend throughout the observed period.

---

### [4] House Type Analysis

Different property categories exhibit distinct pricing patterns and market behavior.

* Apartments generally command the highest average price per square meter.

* Villas account for a significant portion of total housing sales.

* Farm properties have comparatively larger average property sizes.

* Holiday houses represent a smaller percentage of the overall housing market.

This analysis helps buyers and investors compare different property categories before making investment decisions.

---

### [5] Property Size Analysis

The scatter analysis demonstrates the relationship between property size and purchase price.

* Larger properties generally have higher purchase prices.

* Price per square meter decreases for certain larger property categories.

* Premium urban properties maintain significantly higher square meter prices despite having smaller areas.

---

### [6] Sales Type Analysis

Different sales categories contribute differently to the overall housing market.

* Regular property sales account for the largest share of transactions.

* Property sales vary considerably across different regions and house types.

* Sales performance can be analyzed interactively using Region, Area, City, House Type, and Sales Type slicers.

---

### [7] Key Influencer Analysis

The Key Influencers visual identifies factors that have the greatest impact on housing prices and market performance.

Some major influencing factors include:

* Region

* House Type

* Property Size (SQM)

* Sales Type

* Purchase Year

These insights enable analysts to understand which variables contribute most significantly to housing prices.

---

### [8] Interactive Dashboard Features

The report includes multiple interactive features including:

* Region Slicer

* Area Slicer

* City Slicer

* House Type Slicer

* Sales Type Slicer

Users can combine multiple filters simultaneously to perform detailed market analysis and compare housing trends across different geographical regions and property categories.

---

### [9] Business Outcome

Using this dashboard, business users can:

* Monitor overall housing market performance.

* Compare regional sales trends.

* Analyze property pricing across different locations.

* Identify high-performing property categories.

* Evaluate Year-to-Date and Last Twelve Months sales.

* Compare average price per square meter across regions.

* Understand market trends using interactive visualizations.

* Support investment decisions using data-driven insights.

Overall, this dashboard provides a comprehensive analytical solution for understanding the housing market, enabling real estate professionals, investors, and business analysts to make informed decisions based on accurate and interactive business intelligence.
