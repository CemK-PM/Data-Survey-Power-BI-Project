# Data Professional Survey Analysis 📊

This repository contains an end-to-end business intelligence project that analyzes the global data professional landscape, focusing on salary trends, tool preferences, and workplace priorities.

## 🛠️ Data Transformation (Power Query)
The raw survey data was highly unorganized and inconsistent. The entire **ETL (Extract, Transform, Load)** process was performed within Power BI's Power Query Editor:

* **Salary Normalization:** Transformed text-based salary ranges (e.g., "40k-65k") into a numeric **"Average Salary"** column to enable quantitative analysis.
* **Category Standardization:** Cleaned and standardized entries for **Job Titles**, **Industries**, and **Countries** by removing "Other (Please Specify)" noise.
* **Data Refinement:** Removed irrelevant technical metadata and ensured all fields were correctly cast into appropriate data types.

## 📁 Project Structure

* **[Power BI Dashboard (PBIX)](data/Data%20Survey%20for%20Github.pbix)**: Main project file.
* **[Cleaned Dataset](data/Data%20Survey%20Cleaned.xlsx)**: Processed and cleaned data.
* **[Raw Survey Data](data/Power%20BI%20-%20Data%20Survey%20Project.xlsx)**: Original raw dataset.

## 🖥️ Dashboard Preview: Data Survey 1
![Data Survey 1 Preview](assets/Data%20Survey%201.png)

## 🎥 Dynamic Demo
*(Video demonstration showing interactive filters and drill-downs)*
![Dashboard Demo Video](assets/dashboard_demo.gif)

## 🚀 Key Insights
* **Tool Dominance:** SQL and Python stand out as the most essential programming languages across all data-related roles.
* **Work-Life Balance:** Analysis reveals that remote work flexibility is often a higher priority than salary increments.
* **Sectors:** Technology and Finance sectors show the highest concentration of high-earning data roles.


