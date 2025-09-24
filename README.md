# Task-2
Create Dashboard for Global Market Sale Using Power Bi.
Power BI Internship Task Report
1. Objective
The objective of this project is to design and develop an interactive Power BI dashboard for analyzing Global Store Sales. The dashboard provides insights into sales by country, store, category, and time, with drill-down features and KPIs for decision-making.
2. Dataset Description
The dataset contains sales transactions from multiple global stores. Key fields include.
- Store Name
- Country
- Product Category
- Quantity
- Unit Price
- Sales Amount (calculated as Quantity × Unit Price)
3. Data Preparation (Power Query)
Steps performed in Power Query:
1. Imported data from Excel/CSV into Power BI Desktop.
2. Removed unnecessary rows/columns and blanks.
3. Changed data types (e.g., Date, Whole Number, Decimal).
4. Created calculated column: SalesAmount = Quantity × UnitPrice.
5. Created dimension tables for Date, Store, and Category.
6. Closed & Applied transformations.
4. Data Modeling
A star schema data model was created:
- Fact table: FactSales (transactions).
- Dimension tables: DimDate, DimStore, DimCategory.
- Relationships established between FactSales and dimension tables.
- A Date table was generated using DAX CALENDAR function and marked as the official date table.
5. DAX Measures
The following key measures were created:

Total Sales = SUM(FactSales[SalesAmount])
Total Quantity = SUM(FactSales[Quantity])
Avg Unit Price = DIVIDE([Total Sales], [Total Quantity], 0)
Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
YoY Growth % = DIVIDE([Total Sales] - [Sales LY], [Sales LY], 0)
% of Total (by Category) = DIVIDE([Total Sales], CALCULATE([Total Sales], ALL('DimCategory')), 0)
6. Dashboard Visuals
The dashboard includes:
- KPI cards for Total Sales, Total Quantity, and Avg Unit Price.
- Slicers for Year and Store selection.
- Monthly trend chart (line/column chart).
- Category distribution (donut chart).
- Top N bar chart by sales.
- Map visual for country-wise sales.
- Drillthrough and tooltip pages for deeper insights.
7. Publishing & Sharing
The report was published to the Power BI Service workspace. Dataset credentials were configured, and scheduled refresh was enabled. The report can be shared with stakeholders via link, PDF export, or by granting access.
8. Conclusion
This Power BI dashboard successfully demonstrates the ability to transform raw sales data into interactive visual insights. It provides management with the tools to analyze sales trends, compare performance across stores and categories, and make data-driven decisions.
