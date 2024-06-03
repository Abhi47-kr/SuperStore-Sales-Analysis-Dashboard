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

## SALES FORECASTING
- **Sales Forecast**: Adding a new page to showcase sales forecast using a line chart visual. This allows to analyze and predict future sales trends based on historical data.
  - DAX Table Creation: Group Sales by Order Date.
  ```DAX
  SalesByDate = SUMMARIZE('Table', 'Table'[Order Date], "Sales", SUM('Table'[Sales]))
  ```
You can view the PDF version of the Superstore Sales Dashboard [here](https://github.com/Abhi47-kr/SuperStore-Sales-Analysis-in-Power-BI/blob/483287175d5dd41a504a6bc985c3e01a85af335b/Super_Store_Sales_Dashboard_.pdf) | For the interactive Superstore Sales Dashboard Dashboard [here](https://app.powerbi.com/view?r=eyJrIjoiYTI3OWI1ZDktMjQ3Ni00OTQ0LWE1MGEtZDVlMjVhNDBhN2U0IiwidCI6Ijg1MDY3ODBjLWIxMjQtNGY3Zi04YTkwLWY4NWRlYzk1NjU5ZCJ9)

## KEY FINDINGS

### Overall Sales and Profitability
- **Total Sales**: The SuperStore has achieved total sales of $1.6 million.
- **Total Profit**: The total profit stands at $175,000.
- **Orders**: The total number of orders processed is 22,000.
- **Shipping Days**: The average shipping time is 4 days.

### Sales by Category
- **Top Categories**:
  - Office Supplies: $640,000
  - Technology: $470,000
  - Furniture: $450,000

### Sales by Sub-Category
- **Leading Sub-Categories**:
  - Phones: $200,000
  - Chairs: $180,000
  - Binders: $170,000
  - Storage: $150,000
  - Accessories: $120,000

### Monthly Sales Trends
- **2019 vs. 2020**: There is a clear year-over-year comparison indicating sales performance each month, showing trends and seasonality.

### Sales by Segment
- **Customer Segments**:
  - Corporate: 48% of total sales
  - Consumer: 33% of total sales
  - Home Office: 19% of total sales

### Sales by Payment Mode
- **Preferred Payment Methods**:
  - Cash on Delivery (COD): 43%
  - Online payments: 35%
  - Card payments: 22%

### Sales by Region
- **Regional Performance**: Sales are distributed across Central, East, South, and West regions with varied performance.

### Top Performing States
- **Top States by Sales**:
  - California: $335,000
  - New York: $187,000
  - Texas: $116,000
  - Washington: $93,000
  - Pennsylvania: $82,000

## ACTIONABLE INSIGHTS AND RECOMMENDATIONS

### Category and Sub-Category Analysis
- **Office Supplies Dominance**: The Office Supplies category has the highest sales, suggesting a strong demand in this area. Focus on promotional strategies for other categories like Technology and Furniture to balance the sales distribution.
- **Sub-Category Focus**: Phones and Chairs are the leading sub-categories. Increasing inventory and marketing efforts in these sub-categories could boost sales further.

### Sales Trends and Seasonality
- **Monthly Sales Trends**: The dashboard shows fluctuations in monthly sales between 2019 and 2020. Identifying reasons for peaks and troughs can help in planning marketing campaigns and inventory management.

### Customer Segmentation
- **Corporate Segment**: With Corporate customers making up almost half of the sales, tailor your sales strategies and product offerings to meet the needs of this segment.

### Payment Methods
- **Cash on Delivery Popularity**: COD is the most popular payment method. Ensuring a smooth COD process and exploring incentives for other payment methods could improve sales and customer satisfaction.

### Regional and State Performance
- **Focus on High Performing States**: California, New York, and Texas are the top-performing states. Strategies to replicate success in these states could be applied to lower-performing regions to boost overall sales.

### Sales Forecast
- **15-Day Forecast**: The sales forecast for the next 15 days can help in demand planning and inventory management. Ensuring sufficient stock levels and timely promotions can help in meeting the forecasted sales targets.

## CONCLUSION
The SuperStore Sales Analysis Dashboard provides a comprehensive view of sales performance, highlighting key areas of strength and opportunities for improvement. By leveraging these insights, the SuperStore can optimize its strategies to drive sales growth and enhance customer satisfaction.

