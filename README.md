# Amazon-Sales-Analysis-Excel-
End-to-end Amazon sales analysis on 50,000 orders using Excel — covers data cleaning, KPI calculations, pivot-based insights, and an interactive dashboard with slicers.
Amazon Sales Analysis Dashboard is a comprehensive Excel-based data analytics project built on a synthetic dataset of 50,000 Amazon orders spanning January 2024 to December 2025. The project walks through the complete data analysis lifecycle — from raw data cleaning to an interactive sales dashboard — using only Microsoft Excel.

🗂️ Workbook Structure
SheetPurposeamazon_sales_datasetRaw + processed dataset (50,000 rows, 18 columns)Data DictionaryColumn definitions, data types, and business useInsightsStep-by-step analysis notes and business insightsQuestions10 business questions driving the analysisDashboard1KPI summary dashboard (Total Sales, Orders, Units, AOV)DashBoardFull interactive pivot dashboard with slicers

📊 Dataset Overview

Rows: 50,000 orders
Date Range: Jan 2024 – Dec 2025
Product Categories: Beauty, Fashion, Books, Electronics, Sports, Home & Kitchen
Regions: Asia, North America, Middle East, Europe
Payment Methods: Wallet, UPI, Debit Card, Cash on Delivery, Credit Card
Price Range: $5 – $500 per unit
Discount Range: 0% – 30%
Rating Scale: 1.0 – 5.0 (Avg: ~3.0)
Total Revenue: ~$32.87 Million


🔑 Key Columns
ColumnDescriptionorder_idUnique order identifierorder_dateDate of order placementproduct_categoryCategory of the product soldpriceUnit selling pricediscount_percentDiscount applied (0–30%)quantity_soldUnits sold per ordercustomer_regionGeographic regionpayment_methodPayment mode usedratingCustomer rating (1–5)total_revenueRevenue = discounted price × quantity

🛠️ Data Processing Steps

Data Cleaning — Fixed incorrect values (e.g., text quantities → numeric), removed empty rows, corrected data types
Feature Engineering — Derived Month_Year using =TEXT(), created sales_range buckets (1–100, 100–500, 500+) and rating_group (High Rated / Low Rated) using nested IF formulas
KPI Calculations — Total Sales, Total Orders, Total Units Sold, Average Order Value, Highest/Lowest Sales using SUM, COUNT, and reference formulas
Pivot Tables — Revenue by category, region, payment method, month, and discount bracket
Dashboard — Two dashboard sheets with KPI cards, charts, and slicers for dynamic filtering


❓ Business Questions Answered

Which month has the highest and lowest sales?
Which product category contributes most/least to revenue?
Which region generates maximum and minimum sales?
Does a higher discount percentage increase revenue?
Which payment method is most/least used?
Are high-rated products ordered more frequently?
How does month-wise sales change across categories? (Slicer)
How does category performance vary by region? (Slicer)
How does discount affect regional revenue? (Slicer)
How are sales distributed across revenue buckets ($0–100, $100–500, $500+)?


💡 Key Insights

Beauty is the top revenue-generating category; Sports is the lowest
January 2025 recorded the peak monthly revenue
0–5% discounts generate the highest revenue (~$6.18M); revenue declines steadily beyond 10%
Wallet is the most used payment method and also generates the highest total revenue
High-rated products receive more orders than low-rated ones
Regional demand patterns and payment preferences vary significantly across Asia, North America, Middle East, and Europe


📈 Charts Used

Line Chart — Monthly sales trends
Doughnut Chart — Category revenue share
Bar Chart — Regional sales comparison
Clustered Column Charts — Payment method and rating analysis
Histogram — Sales distribution across revenue buckets


🧰 Tools & Techniques
Microsoft Excel · Pivot Tables · Pivot Charts · Slicers · IF / Nested IF · COUNTIF · SUM / COUNT · TEXT() · Data Cleaning · KPI Dashboard Design
