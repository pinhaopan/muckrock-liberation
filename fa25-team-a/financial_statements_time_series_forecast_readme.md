## Overview
This Jupyter Notebook (`financial_statements_.ipynb`) performs financial data analysis and preprocessing on multiple structured financial datasets, with a focus on preparing time-series data for forecasting and visualization. The project involves cleaning, normalizing, and formatting financial statements and revenue reports from various global regions (Europe, Korea, Japan) for further analytical modeling.

## Project Structure

### Data Sources
The analysis uses the following structured datasets located in the `data/` directory:

- **Financial Statements**
  - Format-1.csv
  - Format-2 (Europe, Korea, Japan).csv
  - Format-3 (Europe, Korea, Japan).csv
  - Format-4.csv

- **Revenue Reports**
  - Navy Revenue (FY16–FY24)
  - Marine Revenue (FY20–FY24)
  - District Revenue

- **Asset Reports**
  - Asset Report (FY20–FY24)

- **Additional Data**
  - `bases.json` – Contains base location information

### Key Features
1. **Data Import & Exploration**  
   - Loads multiple CSV and JSON files into pandas DataFrames.
   - Examines structure, unique values, and data integrity.

2. **Data Preprocessing**  
   - Normalizes inconsistent financial entries (e.g., OCR errors, extra spaces, typos).
   - Converts formatted string values (e.g., `"2,38,22,204.63"`) to numeric floats.
   - Standardizes date columns into datetime objects for time-series analysis.

3. **Financial Data Cleaning**  
   - Fixes naming inconsistencies in `Details` column (e.g., `"Accru.ed Liabilities"` → `"Accrued Liabilities"`).
   - Handles region-specific financial data (Europe, Korea, Japan) with uniform formatting.

4. **Time-Series Preparation**  
   - Creates `MonthYearString` and `Last_Day_Date` columns for consistent date indexing.
   - Formats numeric columns for plotting and modeling.

5. **Visualization Setup**  
   - Configures `matplotlib` and `seaborn` for consistent and appealing visualizations.
   - Prepares data for trend analysis, forecasting, and comparative regional studies.

## Libraries Used
- `pandas` – Data manipulation
- `numpy` – Numerical operations
- `matplotlib` & `seaborn` – Data visualization
- `datetime` – Date handling
- `re` – Regular expressions for string cleaning

## Usage
1. Ensure all data files are placed in the correct `data/` subdirectories.
2. Run the notebook cells sequentially to:
   - Load and inspect data
   - Clean and normalize financial entries
   - Convert and format dates and numeric values
   - Prepare data for time-series analysis
3. Use the processed DataFrames (`fs1`, `fs4`, etc.) for further analysis or forecasting models.

## Time Series Forecasting Implementation

The notebook prepares the financial data for time series forecasting through several key steps:

### 1. **Data Preparation for Forecasting**
   - **Date Standardization**: All financial records are standardized with proper datetime formatting using `MonthYearString` and `Last_Day_Date` columns, creating a consistent time index for time series analysis.
   - **Numeric Conversion**: Financial values stored as strings (e.g., "12,30,686.37") are converted to float format using the `formate_value()` function, making them suitable for mathematical operations and modeling.

### 2. **Time Series Structure**
   - **Granular Data**: The dataset includes monthly financial data from March 2023 to December 2023, providing sufficient temporal granularity for short to medium-term forecasting.
   - **Regional Segmentation**: Data is organized by region (Europe, Korea, Japan), allowing for comparative time series analysis across different geographical areas.
   - **Location-specific Tracking**: Individual base locations within regions are tracked separately, enabling granular forecasting at the facility level.

### 3. **Forecast-Ready Features**
   - **Revenue Streams**: The data includes multiple revenue categories (Gaming Revenue, Navy Revenue, Marine Revenue) that can be forecasted independently or as aggregate series.
   - **YTD Tracking**: Year-to-date (YTD) columns provide cumulative metrics that can be used for growth rate calculations and trend analysis.
   - **Seasonality Indicators**: Monthly data allows for identification of seasonal patterns and cyclical trends in financial performance.

### 4. **Data Quality for Prediction**
   - **Missing Value Handling**: Zero values are preserved where appropriate (e.g., regions with no activity) rather than being converted to NaN, maintaining data integrity.
   - **Consistent Frequency**: All records follow a monthly frequency, creating a regular time series suitable for standard forecasting models.
   - **Outlier Identification**: The preprocessing stage allows for potential outlier detection before modeling.

### 5. **Forecasting Methodology Foundations**
   The prepared data structure supports various forecasting approaches:
   - **Univariate Models**: Individual revenue streams can be forecasted using ARIMA, Exponential Smoothing, or Prophet models.
   - **Multivariate Analysis**: Relationships between different revenue categories can be explored for more complex forecasting.
   - **Regional Forecasting**: Comparative forecasts can be generated across Europe, Korea, and Japan to identify regional growth patterns.
   - **Hierarchical Forecasting**: Predictions can be made at multiple levels (individual bases → regions → total).

### 6. **Prediction Applications**
   The cleaned data enables forecasting of:
   - Monthly gaming revenue trends by region
   - Seasonal patterns in military base revenues
   - Year-end revenue projections using YTD data
   - Growth rate comparisons between European, Korean, and Japanese operations
   - Budget planning and financial resource allocation

## Notes
- The data was initially extracted from PDFs using Adobe Express and OCR tools, leading to some formatting inconsistencies that are corrected in this notebook.
- Financial values are stored in Indian numbering format (e.g., `2,38,22,204.63`), which is parsed into float values.
- The notebook is structured to support scalability—additional regions or formats can be integrated following the same preprocessing steps.
- The time series data is now ready for implementation of forecasting models such as ARIMA, SARIMA, Prophet, or machine learning approaches like LSTM networks for financial prediction.


## Overview

This Jupyter Notebook (financial_statements_time_series_forecast.ipynb) performs time series analysis and forecasting on financial statements data from military bases worldwide. The project involves cleaning, preprocessing, and analyzing historical revenue data to predict future monthly revenue trends using statistical forecasting models.

## Project Structure

### Key Features

1. **Data Import & Exploration**
Loads multiple CSV and JSON files into pandas DataFrames.
Examines structure, unique values, and data integrity.

2. **Data Preprocessing**
Normalizes inconsistent financial entries (e.g., OCR errors, extra spaces, typos).
Standardizes military base names and corrects typographical errors.
Converts formatted string values (e.g., "435,381.00") to numeric floats.

3. **Categorization & Enrichment**
Categorizes locations by military branch (Navy, Marines, Army, Air Force, Total).
Groups locations by geographic region (Europe, Korea, Japan, Singapore, Other).
Creates consolidated monthly revenue metrics by summing across regions.

4. **Time-Series Preparation**
Creates proper datetime columns for consistent time-series analysis.
Formats data for compatibility with forecasting libraries.

5. **Forecasting Implementation**
Implements multiple statistical forecasting models.
Generates 12-month revenue predictions for each base location.

## Libraries Used
- pandas – Data manipulation
- numpy – Numerical operations
- matplotlib & seaborn – Data visualization
- datetime – Date handling
- re – Regular expressions for string cleaning
- statsforecast – Statistical forecasting models
- utilsforecast – Evaluation and plotting utilities

## Usage

1. Ensure all data files are placed in the correct data/ subdirectories.
2. Run the notebook cells sequentially to:
- Load and inspect data
- Clean and normalize financial entries
- Convert and format dates and numeric values
- Prepare data for time-series analysis
- Train forecasting models and generate predictions
3. Use the processed DataFrames and forecast results for strategic planning and analysis.

## Time Series Forecasting Implementation

1. Forecasting Models Applied

The notebook implements four statistical forecasting models:
- **Naïve Method**: Uses the last observed value as the forecast
- **Historic Average**: Uses the mean of all historical observations
- **Window Average (3-month)**: Uses the average of the last 3 months
- **Seasonal Naïve (12-month seasonality)**: Uses the value from the same month in the previous year

2. Forecasting Parameters
- **Horizon**: 12 months (predicts revenue for the next full year)
- **Season Length**: 12 months (accounts for yearly seasonal patterns)
- **Window Size**: 3 months (considers previous quarter for predictions)
- **Frequency**: Monthly data ("MS" - Month Start)

3. Data Preparation for Forecasting
- **Time Index Standardization**: Financial records are standardized with proper datetime formatting for consistent time series analysis.
- **Numeric Conversion**: Financial values stored as strings are converted to float format using the clean_currency_value() function.
- **Data Structure**: Data is structured with required columns: unique_id (Locations), ds (Date), and y (Monthly_Revenue).

4. Model Training & Prediction
- **Training Phase**: Models are trained on historical data from March 2023 to December 2023.
- **Prediction Phase**: Each model generates 12-month forecasts for each base location.
- **Comparative Analysis**: Different forecasting methods provide varying predictions, allowing for comparative analysis.

5. Forecast Results
- The system generates forecasts for 38 unique base locations.
Predictions include individual forecasts for bases like "AFRC Dragon Hill Lodge", "Yokosuka Navy", "Camp Humphreys", etc.
Total Gaming Revenue is also forecasted as an aggregate metric.

6. Visualization & Analysis
- Time series plots visualize historical revenue trends.
Comparative plots show different forecasting methods' predictions.
Analysis reveals a generally upward trend in total gaming revenue with steady quarterly growth.

## Analytical Insights

1. **Revenue Trends**:
Total gaming revenue shows a consistent upward trend with minor quarterly fluctuations.
Different military branches show varying revenue patterns.
Regional analysis reveals different growth rates between Europe, Korea, and Japan.

2. **Forecasting Performance**:
The Seasonal Naïve model shows particular promise for capturing seasonal patterns in military base revenue.
Different models provide a range of predictions, useful for creating forecast confidence intervals.
The 3-month Window Average provides smoother predictions than the simple Naïve method.

3. **Strategic Applications**:
Budget Planning: Forecasts support resource allocation decisions.
Growth Analysis: Identifies high-growth regions and bases.
Performance Monitoring: Enables comparison between actual and predicted revenues.

## Notes
The data was initially extracted from PDFs using Adobe Express and OCR tools, leading to some formatting inconsistencies that are corrected in this notebook.
Financial values from different regions (Europe, Korea, Japan) are consolidated into unified monthly revenue metrics.
The forecasting approach is scalable—additional regions, formats, or forecasting models can be integrated following the same workflow.
The time series analysis is now ready for implementation of more advanced forecasting models such as AutoARIMA, Prophet, or machine learning approaches.