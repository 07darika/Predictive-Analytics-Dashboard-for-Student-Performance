# Predictive Analytics Dashboard for Student Performance Using Power BI

## Project Overview
This project focuses on analyzing historical student performance data and building a predictive analytics dashboard using Power BI. The dashboard provides insights into student academic performance and predicts future math scores based on reading scores, writing scores, and test preparation data.

The project demonstrates data cleaning, preprocessing, visualization, and predictive modeling techniques using Power BI and DAX.

---

# Objectives
- Analyze historical student performance data
- Identify patterns and trends in student scores
- Build a predictive model for math score forecasting
- Visualize insights using interactive dashboards
- Evaluate prediction accuracy

---

# Dataset Information
Dataset Used:
`StudentsPerformance.csv`

Dataset Features:
- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch Type
- Test Preparation Course
- Math Score
- Reading Score
- Writing Score

---

# Tools & Technologies
- Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)
- Data Visualization Techniques

---

# Data Preprocessing
The following preprocessing steps were performed:

- Removed blank rows and duplicates
- Verified and corrected data types
- Renamed columns for better readability
- Created calculated columns:
  - AverageScore
  - Result (Pass/Fail)
  - PredictedMathScore
  - PerformanceCategory
- Added StudentID using Index Column

---

# Dashboard Features

## Page 1 — Student Performance Analysis
This page provides historical data analysis and insights.

### Included Visuals
- KPI Cards
  - Total Students
  - Average Math Score
  - Average Reading Score
  - Average Writing Score
  - Pass Percentage

- Gender-wise Student Performance
- Impact of Test Preparation
- Reading vs Writing Correlation
- Student Distribution by Lunch Type
- Interactive Filters/Slicers

---

## Page 2 — Predictive Analytics
This page focuses on forecasting and predictive analysis.

### Included Visuals
- Actual vs Predicted Student Performance
- Pass vs Fail Distribution
- Prediction Accuracy Gauge
- Top Performing Students Table
- Performance Category Analysis

---

# DAX Calculations Used

## Average Score
```DAX
AverageScore =
(StudentsPerformance[MathScore] +
StudentsPerformance[ReadingScore] +
StudentsPerformance[WritingScore]) / 3
```

## Result Column
```DAX
Result =
IF(StudentsPerformance[AverageScore] >= 40,
"Pass",
"Fail")
```

## Predicted Math Score
```DAX
PredictedMathScore =
(StudentsPerformance[ReadingScore] * 0.45)
+
(StudentsPerformance[WritingScore] * 0.45)
+
IF(
StudentsPerformance[test preparation course] = "completed",
5,
0
)
```

## Performance Category
```DAX
PerformanceCategory =
SWITCH(
TRUE(),
StudentsPerformance[MathScore] >= 80, "Excellent",
StudentsPerformance[MathScore] >= 60, "Good",
StudentsPerformance[MathScore] >= 40, "Average",
"Poor"
)
```

---

# Key Insights
- Students who completed test preparation courses performed better overall.
- Reading and writing scores show strong positive correlation.
- Students with standard lunch plans generally scored higher.
- Most students fall under the “Good” and “Excellent” performance categories.
- The predictive model achieved high prediction accuracy.

---

# Expected Outcome
This project helps in understanding:
- Predictive analytics concepts
- Trend forecasting
- Business intelligence reporting
- Dashboard design
- Data-driven decision making

---

# Conclusion
The Student Performance Prediction Dashboard successfully demonstrates how historical educational data can be transformed into meaningful insights using Power BI. The project combines analytics, forecasting, and visualization techniques to create an interactive and professional business intelligence solution.

---

# Author
**Darika S**

---

# Project Title
**Predictive Analytics Dashboard for Student Performance Using Power BI**
