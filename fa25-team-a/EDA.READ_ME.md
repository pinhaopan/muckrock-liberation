# Fiscal Year Revenue Data Analysis

## 📘 Overview

This project explores a dataset containing fiscal year revenue information, focusing on data cleaning, type conversion, missing value analysis, and exploratory visualization. The analysis aims to prepare the data for quantitative modeling and uncover preliminary insights into revenue trends across fiscal years.

---

## 🧩 Data Summary

- **Initial Data Types:**  
  All columns in the original DataFrame were stored as `object` data types, requiring conversion to appropriate numeric or categorical formats for analysis.

- **Missing Values:**  
  Several columns contained missing values.  
  - *Installation* had the highest percentage of missing data (**12.05%**).  
  - Fiscal year columns ranged between **8.43% – 9.64%** missing values.  
  - *Country* had the lowest percentage of missing values (**1.20%**).

- **Data Cleaning Challenges:**  
  Fiscal year columns contained non-numeric entries such as hyphens (`'-'`) and text strings (`'FY16 '`), which required removal or conversion before numerical analysis.

---

## 📊 Key Findings

- **Data Conversion:**  
  After cleaning and type conversion, the fiscal year revenue data was successfully converted into numeric format, enabling descriptive and correlation-based analysis.

- **Distribution Patterns:**  
  Histograms and box plots revealed **varying revenue distributions** across fiscal years, with several **potential outliers** suggesting substantial variance among entities.

- **Correlation Analysis:**  
  A **strong positive correlation** was observed between consecutive fiscal year revenue columns, indicating consistent performance trends over time.

---

## 🔍 Insights & Next Steps

1. **Handle Missing Data:**  
   Address missing values through **imputation** or **removal**, depending on their distribution and impact on downstream analysis.

2. **Validate Conversions:**  
   Confirm that all fiscal year columns were correctly converted to numeric values, ensuring data integrity for future computations.

3. **Outlier Investigation:**  
   Examine identified outliers to determine if they represent genuine anomalies or errors. Based on findings, consider appropriate handling methods such as **removal**, **capping**, or **log transformation**.

4. **Next Phase:**  
   With a cleaned and consistent dataset, proceed to **quantitative modeling**, trend forecasting, or regression-based revenue prediction.

## 🧭 Navigating the Jupyter Notebook

The main analysis is contained in **`DS701 EDA Assignment.ipynb`**, which is organized into clearly labeled sections. Each section performs a distinct EDA task:

### 1. **Data Loading**
- Mounts Google Drive and loads the Excel dataset.  
- Displays the first few rows (`df.head()`), data types (`df.info()`), and summary statistics (`df.describe()`).

### 2. **Missing Value Analysis**
- Calculates and prints the **count** and **percentage** of missing values per column.  
- Visualizes missing data using a **heatmap** for quick identification of incomplete fields.

### 3. **Distribution Analysis**
- Converts fiscal year columns to numeric format, handling `'-'` and non-numeric strings.  
- Creates **histograms** for revenue columns and **bar plots** for categorical variables such as *Country* and *Installation*.

### 4. **Relationship Exploration**
- Builds a **correlation matrix heatmap** showing relationships between fiscal year revenues.  
- Generates **scatter plots** for selected year pairs to visualize linearity and strength of correlation.

### 5. **Outlier Detection**
- Uses **box plots** across fiscal year columns to identify outliers and assess data variability.

### 6. **Summary & Recommendations**
- Summarizes all key findings (missing data, correlations, outliers).  
- Provides **next-step recommendations** for handling missing data, refining conversions, and preparing for predictive modeling.

---
