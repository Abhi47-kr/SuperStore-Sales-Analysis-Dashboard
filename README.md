# SUPERSTORE SALES ANALYSIS DASHBOARD

## TABLE OF CONTENTS
1. [Project Objective](#project-objective)
2. [Data Sources](#data-sources)
3. [Tool Used](#tool-used)
4. [ETL Process](#etl-process)
5. [Sales Dashboard](#sales-dashboard)
6. [Sales Forecasting](#sales-forecasting)
7. [Key Findings](#key-findings)
8. [Actionable Insights and Recommendations](#actionable-insights-and-recommendations)
9. [Conclusion](#conclusion)

## PROJECT OBJECTIVE
To enhance business success by applying data analysis techniques, with an emphasis on *Time Series Analysis*, to deliver meaningful insights and precise *Sales Forecasting* through an interactive Dashboard.

## DATA SOURCES
The dataset is a US-based SuperStore Sales dataset which is in an Excel file. You can access the dataset [here](https://github.com/Abhi47-kr/SuperStore-Sales-Analysis-in-Power-BI/blob/93a9f3667815aaa7039dbc476c0284009cbe2240/SuperStore%20Sales%20DataSet.xlsx).

## TOOL USED
- Power BI
- Power Query Editor
- DAX (Data Analysis Expressions)

## ETL PROCESS
Data Extraction, Transformation, and Loading

### Data Extraction
- **Source**: SuperStore Sales dataset Excel file.
- **Action**: Imported the data from the Excel file into Power BI.

### Data Transformation (Power Query)
- Utilized Power Query Editor to ensure proper data types, handle errors, remove duplicates, and apply necessary transformations to clean and structure the data.

### Load Data
- Apply the transformations and load the cleaned data into Power BI report view.

## SALES DASHBOARD
1. **Visual Customization**: Changing the canvas background to enhance the overall look and feel of the dashboard.
2. **Clustered Bar Chart**: Creating clustered bar charts to visualize sales by category and subcategory. This allows for easy comparison and identification of trends.
3. **Stacked Area Chart**: To compare sales and profit year over year. Analyzing monthly sales and profit trends provides insights into performance patterns.
   - **Add Month Column**: Used DAX to create a new column that extracts the month from the order date.
   ```DAX
   Month = FORMAT('Table'[Order Date], "MMMM")
   ```
4. **Map Visualization**: Displaying state-wise sales and profit using a map.
5. **Donut Chart**: To showcase sales by payment mode.
6. **Pie Chart**: To showcase sales by segment.
7. **Slicer**: To filter the report by region and year.
8. **Display the KPIs using Card**: Sum of Sales, Profit, Quantity, Average Ship Days.
   - Add Ship Days Column: Use DAX to calculate the number of days taken to ship an order.
   ```DAX
   Ship Days = DATEDIFF('Table'[Order Date], 'Table'[Ship Date], DAY)
   ```

## Sales Forecasting
- **Sales Forecast**: Adding a new page to showcase sales forecast using a line chart visual. This allows to analyze and predict future sales trends based on historical data.
  - DAX Table Creation: Group Sales by Order Date.
  ```DAX
  SalesByDate = SUMMARIZE('Table', 'Table'[Order Date], "Sales", SUM('Table'[Sales]))
  ```
You can view the PDF version of the Superstore Sales Dashboard [here](https://github.com/Abhi47-kr/SuperStore-Sales-Analysis-in-Power-BI/blob/483287175d5dd41a504a6bc985c3e01a85af335b/Super_Store_Sales_Dashboard_.pdf) | For the interactive Superstore Sales Dashboard Dashboard [here](https://app.powerbi.com/view?r=eyJrIjoiYTI3OWI1ZDktMjQ3Ni00OTQ0LWE1MGEtZDVlMjVhNDBhN2U0IiwidCI6Ijg1MDY3ODBjLWIxMjQtNGY3Zi04YTkwLWY4NWRlYzk1NjU5ZCJ9)

  
