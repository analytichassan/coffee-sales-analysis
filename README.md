# ☕ Coffee Sales Analysis — Excel Dashboard
An end-to-end Excel project that turns 1,000 raw coffee orders into a formatted interactive sales dashboard, covering data cleaning, table lookups, pivot tables and business insights.
# 📌 Project Overview
The raw data came in three separate tables which are Orders, Customers, and Products, with the Orders table missing several key fields (customer name, email, country, coffee type, roast type, size, unit price, sales). The goal was to merge everything into a single clean dataset, then build a dashboard that answers the following business questions; where are we selling well, what is driving revenue, and is our loyalty program actually working?
### Tool used
Microsoft Excel (formulas, PivotTables, PivotCharts, Slicers)
# 🧹 Data Preparation
- Merged customer data into Orders using XLOOKUP (customer name, email, country)
- Merged product data into Orders using INDEX/MATCH (coffee type, roast type, size, unit price)
- Fixed broken emails: after the lookup, some emails returned "0" for missing records so i cleaned with an IF function
- Calculated Sales as Unit Price × Quantity
- Decoded abbreviations: coffee type and roast type came in as short codes, so I built new columns with IF statements to convert them into readable full names (e.g. "Rob" → "Robusta")
- Standardized dates to a DD-MMM-YYYY style format to avoid US/European date confusion
- Formatted numbers: bag sizes in kg, Unit Price and Sales as USD currency
- Checked for and removed duplicates
- Transformed the range into an Excel Table for more convenient referencing and dynamic pivot table sources.
# 📊 Dashboard Build
Using PivotTables built on the cleaned Orders table, I created:
- Total Sales Over Time using line chart with a Timeline filter on Order Date
- Sales by Country using bar chart
- Top 5 Customers using bar chart
- Slicers for Coffee Size, Roast Type, and Loyalty Card so the whole dashboard filters interactively

All visuals were then assembled onto a single dedicated Dashboard sheet, styled with a consistent color theme and layout.
