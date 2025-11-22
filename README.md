1. Project Overview

This project analyzes Siddharth Associates’ import data to deliver insights on:

YoY import performance

Category & sub-category contribution

Supplier activity (Active vs Churned)

Unit economics

Pareto analysis for top HSN codes

The solution was built using:

Python (data cleaning + feature engineering)

SQL (business logic queries)

Power BI (interactive dashboards & visuals)

This README explains the project workflow, files included, and how to reproduce the analysis.

2. Data Pipeline Summary

The workflow follows a three-stage pipeline:

Stage 1 — Python Data Cleaning & Parsing

Standardized column names

Cleaned and normalized Goods Description

Extracted:

Model Name

Model Number

Material Type

Capacity

Embedded Quantity

Standardized units

Exported cleaned_trade_data.csv

Stage 2 — Python Feature Engineering

Performed business rule calculations:

Grand Total INR

Landed Cost Per Unit (LCPU)

Category mapping (HSN → Category)

Subcategory mapping (keywords)

Final export: final_feature_engineered_data.csv

This is the primary dataset used in Power BI.

Stage 3 — Power BI Visualization

A 5-page dashboard using trade_cleaned table (from final CSV):

Macro Trends

Category Drilldown

Supplier Overview

Unit Economics

Pareto Analysis (HSN)

All visuals are powered through measures and calculations built inside Power BI using DAX.


3. Files Included in Submission
1. Python Scripts

data_cleaning_parsing.py

feature_engineering.py

These scripts generate the cleaned and enriched dataset.

4. Power BI Dashboard Structure
📌 Page 1: Macro Trends

Total Value / Duty Paid / Grand Total

YoY trend line

YoY % matrix

📌 Page 2: Category Drilldown

Treemap (Category → Subcategory)

Stacked bar chart

Category-wise breakdown

📌 Page 3: Supplier Overview

Total, active, churned suppliers

Import value by IEC

Supplier drilldown table

📌 Page 4: Unit Economics

LCPU

Unit price

Cost & value trend

Category-wise LCPU comparison

📌 Page 5: Pareto Analysis (HSN)

HSN ranking

Cumulative contribution %

Pareto (bar + line)

Top HSN contributors


How to Run the Python Scripts
In Google Colab:

1.Upload the Excel file

2.Upload the scripts

Run:
  python data_cleaning_parsing.py
  python feature_engineering.py
On VS Code:

1.Install Python 3.10+

2.Install dependencies:
  pip install pandas openpyxl
Run:
  python data_cleaning_parsing.py
  python feature_engineering.py


6. How to Load Data into Power BI

1.Open final_feature_engineered_data.csv

2.Rename table → trade_cleaned

3.Create measures, pages, and visuals using trade_cleaned
