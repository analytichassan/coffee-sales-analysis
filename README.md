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
# 💡 Key Insights
- The United States drives 79% of total sales, versus 15% in Ireland and 6% in the UK. The US also has the highest average sale per order line ($46 vs $44 in Ireland and $38 in the UK) leading on both volume and order size.
- Sales are fairly even across coffee types, with Excelsa and Liberica narrowly ahead of Arabica and Robusta trailing (it's the lowest priced option). By roast, Light roast outsells Medium and Dark. By size, the 2.5kg bag alone accounts for roughly half of all sales. bulk purchases are the single biggest revenue driver.
- Non-loyalty customers generated more total sales ($24.2K vs $20.9K) and a higher average order value ($46.48 vs $43.67) than loyalty cardholders which is the opposite of what a loyalty program is meant to do.
- There isn't a single "whale" account among the top five customers, who are all in a narrow $278–$317 range. Compared to a revenue profile supported by a few large spenders, that one is healthier and less risky.
