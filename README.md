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

## 🧠 Technical Highlights: DAX Logic
To add advanced functionality and dynamic insights to the dashboard, I developed custom DAX measures:

### 1. Dynamic Bar Coloring (Conditional Formatting)
Automatically highlights the Highest (Green) and Lowest (Red) salaries in the visual based on the current filtered view.

Min Max Bar Color = 
VAR CurrentSalary = AVERAGE('Data Professional Survey'[Average Salary]) 
VAR AllSalaries = 
    CALCULATETABLE(
        VALUES('Data Professional Survey'[Q1 - Which Title Best Fits your Current Role?.1]),
        ALLSELECTED('Data Professional Survey')
    )
VAR MinSalaryInView = 
    MINX(AllSalaries, CALCULATE(AVERAGE('Data Professional Survey'[Average Salary])))
VAR MaxSalaryInView = 
    MAXX(AllSalaries, CALCULATE(AVERAGE('Data Professional Survey'[Average Salary])))

RETURN
    SWITCH( TRUE(),
        ISBLANK(CurrentSalary), "#A6A6A6",
        CurrentSalary = MaxSalaryInView, "#006644", 
        CurrentSalary = MinSalaryInView, "#D38B7D", 
        "#A6A6A6" 
    )

### 2. Dynamic Top Job Priority
Identifies the #1 most important factor for job seekers within the selected demographic.

Top Job Priority = 
TOPN(
    1, 
    VALUES('Data Professional Survey'[Q8 - If you were to look for a new job today, what would be the most important thing to you?]), 
    CALCULATE(COUNT('Data Professional Survey'[Q8 - If you were to look for a new job today, what would be the most important thing to you?])), 
    DESC
)

### 3. Difficulty Index Mapping
Converts qualitative survey responses into a sortable numeric scale to enable ranking and average difficulty calculations.

Difficulty_order_ = 
SWITCH('Data Professional Survey'[Q7 - How difficult was it for you to break into Data?],
    "Very Easy", 1,
    "Easy", 2,
    "Neither easy nor difficult", 3,
    "Difficult", 4,
    "Very Difficult", 5,
    6
)

## 🚀 Key Insights
* **Tool Dominance:** SQL and Python stand out as the most essential programming languages across all data-related roles.
* **Work-Life Balance:** Analysis reveals that remote work flexibility is often a higher priority than salary increments.
* **Sectors:** Technology and Finance sectors show the highest concentration of high-earning data roles.
