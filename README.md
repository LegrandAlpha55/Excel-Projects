<img width="2351" height="2268" alt="image" src="https://github.com/user-attachments/assets/64367aa1-646d-4c47-978d-3d84fb759fcb" />Sales Data Cleaning, Analysis, and Dashboard
Project Overview
This project demonstrates an end-to-end sales data analysis workflow, beginning with a raw CSV dataset and progressing through data cleaning, analysis, and dashboard development in Microsoft Excel.

The main objectives of the project were to:

Inspect the quality and structure of the raw sales data.
Identify missing, duplicated, inconsistent, and invalid values.
Clean and standardize the dataset.
calculate total sales for each transaction.
Summarize sales performance using PivotTables.
Build an interactive Excel dashboard.
Present insights by category, product, region, month, and salesperson.
Repository Files
File	Description
Sales_transactions_2022_2025.csv	Original raw sales dataset containing formatting problems, missing values, duplicates, and invalid entries.
Sales (Cleaned_Data).xlsx	Cleaned and standardized version of the sales dataset.
Sales Analysis and Dashboard.xlsx	Excel workbook containing PivotTable analysis, charts, slicers, and the final dashboard.
Data Workflow
The project follows this workflow:

Raw data collection

Sales transaction data was provided in CSV format.
Data profiling

Columns, data types, missing values, duplicates, and inconsistent entries were inspected.
Data cleaning

Text values were standardized.
Dates and numerical values were corrected.
Missing values were handled.
Total sales were recalculated.
Data analysis

PivotTables were created to summarize important sales metrics.
Dashboard development

Charts and slicers were used to create an interactive Excel dashboard.
1. Raw Dataset
File
Sales_transactions_2022_2025.csv

Dataset Dimensions
Rows: 126
Columns: 9
Unique order IDs: 120
Fully duplicated rows: 6
Duplicated order IDs: 6
Although the filename contains 2022_2025, the cleaned transaction dates available in the workbook range from January 1, 2025, to April 10, 2025.

Raw Data Schema
Column	Raw Data Type	Description	Data Quality Observations
Order ID	Text	Unique identifier assigned to a sales transaction.	No missing values, but duplicated order IDs are present.
Order Date	Text	Date on which an order was recorded.	Contains missing values, whitespace, invalid dates, and multiple date formats.
Product Name	Text	Name of the product sold.	Contains inconsistent spacing around some product names.
Category	Text	Product category.	Contains inconsistent capitalization and extra spaces.
Region	Text	Sales region associated with the order.	Contains missing values, inconsistent capitalization, and extra spaces.
Salesperson	Text	Employee responsible for the sale.	Contains inconsistent capitalization and unnecessary spaces.
Quantity Sold	Text	Number of product units sold.	Contains missing values, text such as five, zero values, and negative values.
Unit Price	Text	Price charged for one unit of a product.	Contains missing values, currency symbols, extra spaces, and invalid text.
Total Sales	Text	Sales amount recorded for the transaction.	Contains missing values, currency symbols, invalid entries, and values that do not always match quantity multiplied by unit price.
Raw Data Quality Issues
Missing Values
Column	Missing Values
Order Date	12
Region	25
Quantity Sold	9
Unit Price	15
Total Sales	11
Duplicate Records
The raw dataset contains:

6 fully duplicated records.
6 repeated order IDs.
120 unique order IDs across 126 rows.
The duplicated records remain relevant when interpreting totals. They should be removed if each order ID is intended to represent one unique transaction.

Inconsistent Text Formatting
Examples of inconsistent text formatting include:

north, North, and values containing extra spaces.
office supplies, Office Supplies, and other capitalization variants.
bob jones and Bob Jones.
Product names containing leading or trailing whitespace.
Inconsistent Date Formats
The Order Date column contains several formats, including:

2025-02-01
2025.03.20
02/05/2025
17.01.2025
2025/01/20
03-15-2025
INVALID_DATE
These formats must be standardized before time-based analysis can be performed reliably.

Invalid Numerical Values
The numerical columns contain entries such as:

five
-3
invalid_price
ERROR
Currency-formatted strings such as $25.00
Values containing unnecessary spaces
These entries prevent the raw columns from being used directly in numerical calculations.

2. Cleaned Dataset
File
Sales (Cleaned_Data).xlsx

Worksheet
Sales_transactions_2025

Cleaned Dataset Dimensions
Rows: 126 populated transaction rows
Columns: 9
Missing values: 0 across the populated records
Unique products: 12
Product categories: 3
Sales regions: 4
Salespeople: 4
Date range: January 1, 2025, to April 10, 2025
The worksheet contains several formatted blank rows below the populated dataset. These rows are not part of the 126 sales transactions.

Cleaned Data Schema
Column	Cleaned Data Type	Description
Order ID	Text	Transaction identifier in the format ORD-####.
Order Date	Date	Standardized date associated with the transaction.
Product Name	Text	Cleaned and trimmed product name.
Category	Text	Standardized product category.
Region	Text	Standardized sales region.
Salesperson	Text	Standardized salesperson name.
Quantity Sold	Integer	Number of units sold.
Unit Price	Decimal	Clean numerical unit price without currency symbols.
Total_Sales	Decimal / Formula	Calculated sales value for each transaction.
The transaction-level sales calculation is:

Total_Sales = Quantity Sold × Unit Price

In the Excel table, the calculated column uses a structured formula equivalent to:

=[@[Quantity Sold]]*[@[Unit Price]]

Cleaning Steps Applied
1. Standardized column names
Column names were made consistent and readable. For example:

Total Sales was changed to Total_Sales.
2. Removed unnecessary whitespace
Leading and trailing spaces were removed from values such as:

Product names
Categories
Regions
Salesperson names
Numerical text values
3. Standardized capitalization
Text values were converted into consistent labels, including:

north to North
office supplies to Office Supplies
bob jones to Bob Jones
ELECTRONICS to Electronics
4. Standardized dates
Different date formats were converted into valid Excel date values so that the data could be grouped and analyzed by month.

5. Converted numerical columns
The following fields were converted from text into numerical values:

Quantity Sold
Unit Price
Total_Sales
Currency symbols and extra spaces were removed before conversion.

6. Handled missing and invalid values
Missing and invalid values in the raw dataset were replaced or corrected to create complete records in the cleaned dataset.

7. Recalculated total sales
The original Total Sales field contained missing, incorrect, and invalid entries. Therefore, total sales were recalculated using quantity and unit price.

8. Formatted the data as an Excel table
The cleaned data was formatted as an Excel table named Sales. This supports:

Structured formulas
Filters
Sorting
PivotTables
Consistent formatting
Easier expansion of the dataset
Cleaned Data Quality Summary
The cleaned workbook contains no missing values across its 126 populated rows.

However, it still contains:

6 duplicated rows.
6 duplicated order IDs.
This means that the cleaned workbook standardizes and completes the data, but duplicate removal should still be considered if the business rule requires one record per order ID.

3. Sales Analysis
File
Sales Analysis and Dashboard.xlsx

Analysis Worksheet
Sales_Analysis

The analysis worksheet uses PivotTables to summarize sales performance across several dimensions.

The analysis includes:

Sales by product category
Sales by product
Average sales by product
Revenue by region
Monthly sales
Salesperson performance
Overall sales amount
Order count
Average sales per order
4. Dashboard
Dashboard Worksheet
Sales_Dashboard

The dashboard provides a visual summary of sales performance using six charts.

Dashboard Visuals
1. Sales per Category
A pie chart named Sales Per Category shows how sales are distributed among:

Electronics
Furniture
Office Supplies
This chart makes it easy to identify the category contributing the largest share of revenue.

2. Top Performing Items
A bar chart named Top Performing Items compares the products generating the highest sales.

This chart helps identify the products that contribute most strongly to overall revenue.

3. Low Performing Items
A bar chart named Low Perfoming Items displays products with lower sales performance.

This chart can support decisions involving:

Product promotion
Inventory planning
Pricing reviews
Product discontinuation or improvement
4. Revenue per Region
A line chart named Revenue Per Region compares revenue across:

East
North
South
West
This visual highlights geographical differences in sales performance.

5. Monthly Sales Trend
An area chart named Montly Sales Trend presents sales performance by month.

The dashboard covers:

January
February
March
April
This chart helps reveal changes in sales over time.

6. Salesperson Performance
A bar chart named Salesperson Perfomance compares the sales generated by:

Alice Smith
Bob Jones
Charlie Brown
Diana Prince
This chart highlights differences in individual sales performance.

Interactive Filtering
The workbook contains slicer components linked to PivotTables. These allow dashboard users to filter the analysis interactively and review specific parts of the data.

5. Key Findings from the Cleaned Dataset
Overall Performance
Metric	Result
Total sales	$43,101.05
Total quantity sold	553 units
Number of transaction rows	126
Unique order IDs	120
These figures include the six duplicated transaction rows that remain in the cleaned workbook.

Sales by Category
Category	Total Sales
Electronics	$23,192.58
Office Supplies	$13,253.63
Furniture	$6,654.84
Insight
Electronics is the highest-performing category, accounting for more sales than Office Supplies and Furniture.

Furniture records the lowest total sales among the three categories.

Sales by Region
Region	Total Sales
South	$14,953.60
East	$10,443.75
North	$10,208.30
West	$7,495.40
Insight
The South is the strongest-performing region, while the West records the lowest sales total.

Sales in the East and North are relatively close.

Salesperson Performance
Salesperson	Total Sales
Diana Prince	$17,752.41
Bob Jones	$13,262.63
Alice Smith	$10,656.58
Charlie Brown	$1,429.43
Insight
Diana Prince is the highest-performing salesperson in the cleaned dataset.

Charlie Brown records the lowest sales total, indicating a large performance difference between the salespeople.

Monthly Sales
Month	Total Sales
January	$21,208.08
February	$9,586.43
March	$8,168.04
April	$4,138.50
Insight
January records the highest sales total.

Sales decrease after January, with April having the lowest total. However, the dataset only includes dates up to April 10, 2025, so April does not represent a complete month.

Product Performance
Rank	Product	Total Sales
1	Ballpoint Pens (12pk)	$7,991.45
2	External Hard Drive	$7,731.34
3	Wireless Mouse	$4,801.91
4	27-inch Monitor	$4,619.90
5	Desk Lamp	$3,047.39
6	Mechanical Keyboard	$2,825.00
7	Ergonomic Chair	$2,799.42
8	USB-C Hub	$2,275.95
9	Notebook A5	$2,214.79
10	Office Chair	$1,992.97
11	Standing Desk	$1,862.45
12	Bluetooth Headset	$938.48
Insight
Ballpoint Pens (12pk) is the highest-performing product by sales, closely followed by External Hard Drive.

Bluetooth Headset records the lowest total sales.

6. Dashboard Data Refresh Note
The PivotTables currently stored in the dashboard workbook display a filtered or earlier snapshot with the following values:

Total sales: $849
Order count: 9
Average sales per order: approximately $94.33
These figures do not match the complete cleaned dataset total of $43,101.05.

This indicates that the dashboard PivotTables may be:

Connected to an earlier or smaller data range.
Displaying a filtered slicer selection.
Using an outdated PivotTable cache.
In need of a data-source update and refresh.
Before presenting the dashboard as the final analysis, the PivotTable source should be linked to the complete Sales table in the cleaned workbook and refreshed. All slicer filters should also be cleared when displaying overall totals.

7. Recommended Improvements
The following improvements would make the project more reliable:

Remove duplicated rows if each order ID should be unique.
Add a duplicate-checking rule based on Order ID.
Connect every PivotTable to the complete cleaned dataset.
Refresh PivotTables before publishing the dashboard.
Clear slicer filters when reporting overall performance.
Use consistent chart title spelling:
Change Low Perfoming Items to Low Performing Items.
Change Montly Sales Trend to Monthly Sales Trend.
Change Salesperson Perfomance to Salesperson Performance.
Add KPI cards for:
Total sales
Total orders
Total quantity sold
Average order value
Best-performing product
Best-performing region
Add a visible note explaining that April contains only partial-month data.
Rename the raw CSV if it only contains 2025 transactions, or add the missing 2022–2024 records if those years were intended to be included.
8. Tools and Techniques
This project uses:

Microsoft Excel
CSV data import
Excel tables
Data cleaning
Structured formulas
PivotTables
PivotCharts
Slicers
Dashboard design
Descriptive sales analysis
Conclusion
This project converts a problematic raw sales dataset into a structured and analysis-ready Excel dataset.

The cleaned data makes it possible to evaluate sales performance by product, category, region, month, and salesperson. The dashboard provides a clear visual summary, while PivotTables support interactive investigation of the sales data.

The analysis shows that:

Electronics is the highest-performing category.
The South is the highest-performing region.
Diana Prince is the highest-performing salesperson.
Ballpoint Pens (12pk) is the highest-performing product.
January has the highest monthly sales.
The dashboard data source or filters should be refreshed before the dashboard is used for final reporting.

Important Note About Power Query Refresh
This project uses Power Query to clean and transform the raw dataset before analysis.

During the cleaning process, issues such as:

Missing values
Inconsistent date formats
Extra spaces
Inconsistent capitalization
Invalid numerical values
were corrected using Power Query transformations.

Refresh Warning
The cleaned workbook is linked to the original raw CSV file. If the source file still contains duplicate records, refreshing the Power Query connection may re-import those duplicate rows into the cleaned dataset.

Therefore:

The current workbook reflects the cleaned version used for the analysis and dashboard.
Refreshing the query without modifying the source CSV may cause duplicate records to reappear.
To permanently prevent duplicates, duplicate records should also be removed from the source dataset or a Remove Duplicates step should be included in the Power Query transformation process.
Recommendation
Before refreshing the workbook:

Verify the source CSV file does not contain unwanted duplicate records.
Review the Power Query steps applied to the dataset.
Confirm that the Remove Duplicates transformation is included if duplicate transactions should not be loaded into the final dataset.
This ensures that the dashboard, PivotTables, and sales metrics remain consistent after future refreshes.
