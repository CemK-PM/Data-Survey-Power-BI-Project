# Data Professional Survey Analysis 📊

This repository contains an end-to-end business intelligence project that analyzes the global data professional landscape, focusing on salary trends, tool preferences, and workplace priorities.

## 🛠️ Data Transformation (Power Query)
The raw survey data was highly unorganized and inconsistent. The entire **ETL (Extract, Transform, Load)** process was performed within Power BI's Power Query Editor:

* **Salary Normalization:** Transformed text-based salary ranges (e.g., "40k-65k") into a numeric **"Average Salary"** column to enable quantitative analysis and statistical comparisons.
* **Category Standardization:** Cleaned and standardized entries for **Job Titles (Q1)**, **Industries (Q4)**, and **Countries (Q11)** by removing "Other (Please Specify)" noise and grouping similar data points.
* **Data Refinement:** Removed irrelevant technical metadata and ensured all fields were correctly cast into appropriate data types for accurate reporting.

## 📁 Project Structure
* **`Data Survey for Github.pbix`**: The primary Power BI file featuring the data model, Power Query transformation steps, and the interactive dashboard.
* **`Data Survey Cleaned.csv`**: The finalized dataset exported after the cleaning process.
* **`Power BI - Data Survey Project.xlsx`**: The original raw survey data for reference.

## 🚀 Key Insights
* **Tool Dominance:** SQL and Python stand out as the most essential programming languages across all data-related roles.
* **Work-Life Balance:** Analysis reveals that remote work flexibility is often a higher priority than salary increments for modern data professionals.
* **Sectors:** The Technology and Finance sectors show the highest concentration of high-earning data roles globally.

## 🖥️ Preview
![Dashboard Preview](dashboard.png)
