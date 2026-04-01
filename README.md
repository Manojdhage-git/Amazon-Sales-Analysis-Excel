# 📦 Amazon Sales Analysis Dashboard — Excel

> End-to-end Amazon sales analysis on 50,000 orders using Excel — covers data cleaning, KPI calculations, pivot-based insights, and an interactive dashboard with slicers.

---

## 📁 Project Overview

**Amazon Sales Analysis Dashboard** is a comprehensive Excel-based data analytics project built on a synthetic dataset of **50,000 Amazon orders** spanning **January 2024 to December 2025**.

The project walks through the complete data analysis lifecycle — from raw data cleaning to an interactive sales dashboard — using only **Microsoft Excel**. It is designed for analysts, students, and business intelligence enthusiasts looking to explore real-world sales data patterns.

---

## 🗂️ Workbook Structure

| Sheet | Purpose |
|---|---|
| `amazon_sales_dataset` | Raw + processed dataset (50,000 rows, 18 columns) |
| `Data Dictionary` | Column definitions, data types, and business use |
| `Insights` | Step-by-step analysis notes and business insights |
| `Questions` | 10 business questions driving the analysis |
| `Dashboard1` | KPI summary dashboard (Total Sales, Orders, Units, AOV) |
| `DashBoard` | Full interactive pivot dashboard with slicers |

---

## 📊 Dataset Overview

| Property | Value |
|---|---|
| Total Records | 50,000 orders |
| Date Range | January 2024 – December 2025 |
| Total Revenue | ~$32.87 Million |
| Avg. Order Value | ~$657 |
| Price Range | $5.01 – $499.99 per unit |
| Discount Range | 0% – 30% |
| Avg. Customer Rating | ~3.0 / 5.0 |

**Product Categories:** Beauty · Fashion · Books · Electronics · Sports · Home & Kitchen

**Customer Regions:** Asia · North America · Middle East · Europe

**Payment Methods:** Wallet · UPI · Debit Card · Cash on Delivery · Credit Card

---

## 🔑 Column Descriptions

| # | Column | Description | Data Type |
|---|---|---|---|
| 1 | `order_id` | Unique identifier for each order | Integer |
| 2 | `order_date` | Date the order was placed | Date |
| 3 | `product_id` | Unique product identifier | Integer |
| 4 | `product_category` | Category the product belongs to | Text |
| 5 | `price` | Original unit selling price | Decimal |
| 6 | `discount_percent` | Discount applied on the product (0–30%) | Integer |
| 7 | `quantity_sold` | Number of units sold per order | Integer |
| 8 | `customer_region` | Geographic region of the customer | Text |
| 9 | `payment_method` | Mode of payment used | Text |
| 10 | `rating` | Customer rating score (1.0–5.0) | Decimal |
| 11 | `review_count` | Total number of customer reviews | Integer |
| 12 | `discounted_price` | Final price after applying discount | Decimal |
| 13 | `total_revenue` | Revenue = discounted price × quantity sold | Decimal |
| 14 | `Month_Year` | Derived: Order month in `mmm-yyyy` format | Text |
| 15 | `sales_range` | Derived: Revenue bucket — `1-100`, `100-500`, `500+` | Text |
| 16 | `rating_group` | Derived: `High Rated` (≥2.5) or `Low Rated` (<2.5) | Text |

---

## 🛠️ Data Processing Steps

### 1. Data Cleaning
- Fixed incorrect values (e.g., text-based quantities like "one" → numeric `1`)
- Removed empty/null rows
- Corrected data types for dates, numbers, and categorical fields

### 2. Feature Engineering
- **`Month_Year`** — Extracted from order date using `=TEXT(B2,"mmm-yyyy")`
- **`sales_range`** — Revenue buckets using nested `IF`:
  ```
  =IF(M2<=100,"1-100", IF(M2>=500,"500+","100-500"))
  ```
- **`rating_group`** — Rating classification using `IF`:
  ```
  =IF(J2>=2.5,"High Rated","Low Rated")
  ```

### 3. KPI Calculations
| KPI | Formula Used |
|---|---|
| Total Sales | `=SUM(amazon_sales_dataset!M2:M50001)` |
| Total Orders | `=COUNT(amazon_sales_dataset!A2:A50001)` |
| Total Units Sold | `=SUM(amazon_sales_dataset!G2:G50001)` |
| Average Order Value | `=Total Sales / Total Orders` |

### 4. Pivot Tables & Charts
- Revenue breakdown by: Category, Region, Payment Method, Month, Discount Range
- Order count vs Revenue comparisons
- Sales distribution histogram

### 5. Interactive Dashboard
- KPI cards (Total Sales, Orders, Units Sold, AOV)
- Charts for trend and comparison analysis
- **Slicers** for dynamic filtering by Category, Region, and Discount Percentage

---

## ❓ Business Questions Answered

1. Which month has the **highest and lowest** sales?
2. Which product category **contributes most and least** to total revenue?
3. Which region generates **maximum and minimum** sales?
4. Does a **higher discount percentage** increase revenue?
5. Which **payment method** is most and least used?
6. Are **high-rated products** ordered more frequently than low-rated ones?
7. How does **month-wise sales performance** change across product categories? *(Slicer)*
8. How does **category performance and payment preference** vary by region? *(Slicer)*
9. How does **discount percentage affect regional** revenue? *(Slicer)*
10. How many sales records fall under **$0–100**, **$100–500**, and **$500+** revenue ranges?

---

## 💡 Key Insights

### 📅 Monthly Sales
- **January 2025** recorded the **highest monthly revenue**
- Monthly revenue shows clear seasonal variation across 2024–2025

### 🛍️ Product Categories
- **Beauty** contributes the **highest share** of total revenue
- **Sports** contributes the **least** to overall revenue

### 🌍 Regional Performance
- Regional demand patterns vary significantly across all four regions
- Asia and North America lead in order volume

### 💸 Discount Impact
- **0–5% discounts** generate the **highest revenue (~$6.18M)**
- Revenue declines steadily beyond **10% discount**
- **30% discount** yields the **lowest revenue (~$4.35M)**
- Higher discounts do **not** reliably increase revenue

### 💳 Payment Methods
- **Wallet** is the most frequently used payment method
- **Wallet** also generates the **highest total revenue** among all payment modes

### ⭐ Ratings & Orders
- **High-rated products** (rating ≥ 2.5) receive significantly more orders than low-rated ones

### 📦 Sales Distribution
- The **majority of sales records** fall in the **$100–500** revenue range
- The **$500+** bucket has the highest total order count (~25,145 records)

---

## 📈 Charts Used

| Question | Chart Type | Reason |
|---|---|---|
| Monthly Sales Trend | Line Chart | Best for time-based trend analysis |
| Category Revenue Share | Doughnut Chart | Shows proportional contribution clearly |
| Regional Sales | Bar Chart | Effective for category comparison |
| Discount vs Revenue | Column Chart | Compares revenue across discount brackets |
| Payment Method Analysis | Clustered Column Chart | Compares order count and revenue side-by-side |
| Rating vs Orders | Clustered Column Chart | Compares order count between rating groups |
| Sales Distribution | Histogram | Shows distribution across revenue buckets |

---

## 🧰 Tools & Techniques Used

- **Microsoft Excel** (2016 or later)
- Pivot Tables & Pivot Charts
- Slicers for dynamic filtering
- Nested `IF` formulas for feature engineering
- `TEXT()`, `SUM()`, `COUNT()`, `COUNTIF()` functions
- KPI Dashboard design
- Data Cleaning & Validation

---

## 🚀 How to Use

1. **Download** and open `Amazon_Sales.xlsx` in Microsoft Excel (2016 or later recommended)
2. Navigate to the **DashBoard** sheet for the full interactive view
3. Use the **Slicers** to filter data by:
   - Product Category
   - Customer Region
   - Discount Percentage
4. Navigate to **Dashboard1** for a quick KPI summary
5. Refer to the **Insights** sheet for detailed analysis notes
6. Refer to the **Data Dictionary** sheet for column definitions

---

## 📂 File Structure

```
Amazon_Sales.xlsx
├── amazon_sales_dataset   → Core data (50,000 rows)
├── Data Dictionary        → Column metadata
├── Insights               → Analysis process & findings
├── Questions              → Business problem statements
├── Dashboard1             → KPI summary view
└── DashBoard              → Full interactive dashboard
```

---

## 📌 Use Cases

- Practice Excel data analysis and dashboard design
- Learn pivot tables, slicers, and chart creation
- Understand e-commerce sales performance metrics
- Portfolio project for data analyst roles

---

## 🙌 Acknowledgements

Dataset is synthetic and created for educational and portfolio purposes. All values are randomly generated to simulate realistic Amazon sales patterns.

