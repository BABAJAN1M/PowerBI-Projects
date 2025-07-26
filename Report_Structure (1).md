
# 📊 Power BI Report Structure: Superstore Sales Dashboard

This markdown file summarizes the structure and logic of the Power BI dashboard built on the Superstore Sales dataset. The dashboard analyzes sales, profit, customer behavior, and shipping performance through 7 core pages.

---

## 1️⃣ Sales Performance Analysis

**🎯 Purpose:** Provide a high-level summary of business performance.

**🔍 Key Questions:**
- What are the total sales, total profit, and number of orders?
- What is the overall profit margin?
- How has revenue trended over time?

**📊 Visuals Used:**
- KPI Cards: Total Sales, Total Profit, Total Orders, Profit Margin
- Line Chart: Sales Trend Over Time
- Clustered Bar Chart: Sales vs Profit by Region
- Slicer: Date range

![Page 1 – Sales Overview](images/Page 1. Sales Performance Analysis.png)

---

## 2️⃣ Regional Sales & Profit Analysis

**🎯 Purpose:** Evaluate performance across locations.

**🔍 Key Questions:**
- Which regions, states, or cities perform best or worst?
- Where are profits negative?

**📊 Visuals Used:**
- Filled Map: Profit and Sales by State
- Bar Chart: Top 10 Cities by Profit
- Heatmap Matrix: Region vs Product Category (with Profit conditional formatting)

![Page 2 – Regional Sales & Profit Analysis](images/Page 2. Regional Sales & Profit Analysis.png)

---

## 3️⃣ Product Insights

**🎯 Purpose:** Drill down into product categories and profitability.

**🔍 Key Questions:**
- Which categories and sub-categories drive the most revenue?
- What are the most and least profitable products?

**📊 Visuals Used:**
- Bar Chart: Sales by Category and Sub-Category
- Tree Map: Sales by Category > Sub-category
- Matrix Table: Profit by Product Name with red-green conditional formatting

![Page 3 – Product Analysis](images/Page 3.Product Analysis.png)

---

## 4️⃣ Customer Segmentation

**🎯 Purpose:** Analyze revenue and discount patterns by customer segments.

**🔍 Key Questions:**
- Which customer segments generate the most revenue?
- Are any segments receiving unusually high discounts?

**📊 Visuals Used:**
- Donut Chart: Segment-wise Sales Share
- Clustered Column + Line Chart: Sales and Average Discount by Segment
- Matrix Table: Segment-wise Sales, Profit, Discount (conditionally formatted)

![Page 4 – Customer Segmentation Analysis](images/Page 4. Customer Segmentation Analysis.png)

---

## 5️⃣ Shipping Impact Analysis

**🎯 Purpose:** Understand how shipping modes affect performance and delivery time.

**🔍 Key Questions:**
- How does shipping mode influence profitability?
- Which shipping mode has the fastest delivery?

**📊 Visuals Used:**
- Bar Chart: Profit by Shipping Mode
- Line/Area Chart: Average Shipping Delay by Mode
- Matrix Table: Shipping Mode-wise Sales, Profit, Orders, Delay Days

**💡 Sample DAX Measures:**
```DAX
Shipping Delay (days) = DATEDIFF(Fact_Orders[Order Date], Fact_Orders[Ship Date], DAY)
Avg Shipping Delay = AVERAGE(Fact_Orders[Shipping Delay (days)])
```

![Page 5 – Shipping Impact Analysis](images/Page 5. Shipping Impact Analysis.png)

---

## 6️⃣ Time-Based Analysis

**🎯 Purpose:** Explore how sales and profits vary over time.

**🔍 Key Questions:**
- What are the peak sales months and weekdays?
- Are there seasonal trends?

**📊 Visuals Used:**
- KPI Cards: Best Month by Sales, Best Weekday by Profit
- Line Chart: Daily Sales Trend
- Bar Charts: Sales by Month, Sales by Weekday

**💡 Sorting Tip:** Custom sort applied on Weekday & Month using calculated columns (`WeekdayNr`, `Month Number`).

![Page 6 – Time-Based Analysis](images/Page 6. Time-Based Analysis.png)

---

## 7️⃣Top Profit & Loss making product analysis

**🎯 Purpose:** Focus on top and bottom product performers.

**🔍 Key Questions:**
- Which products are loss-making?
- What are the top 10 and bottom 10 products by profit?

**📊 Visuals Used:**
- Bar Chart: Top 10 Products by Sales
- Bar Chart: Top 10 Products by Profit
- Bar Chart: Bottom 10 Products by Profit (Loss-Making Products)

**💡 DAX Sample:**
```DAX
Loss-Making Sales = CALCULATE([Total Sales], FILTER(Fact_Orders, Fact_Orders[Profit] < 0))
```

![Page 7 – Top Profit & Loss making products](images/Page 7. Top Profit & Loss making products.png)

![Page 8 – Report Overview ](images/Page 8. Report Overview & Business Questions.png)

---

## 🧠 Design Notes

- Fully normalized star schema with Dim and Fact tables
- All pages use consistent formatting and color themes
- Slicers and filters used where appropriate for better interactivity

---

## 📁 Files Included in Repository

- `Superstore_Sales_Report.pbix` – Main Power BI Report
- `Report_Structure.md` – This file
- `SuperstoreSample.csv` – Raw Dataset
- Screenshots of each report page (optional for preview on GitHub)

---

## 🎯 Summary

This Power BI report demonstrates a deep understanding of:

- Data modeling (star schema)
- DAX Calculations & Measures
- Business-driven insights & KPI definition
- Data storytelling with Interactive visuals
- UI/UX formatting and filters

---
