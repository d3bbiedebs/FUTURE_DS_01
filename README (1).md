# 📊 Business Sales Performance Analytics

> **Task 1 – Future Interns Data Science & Analytics (2026)** · Author: **Debra**
>
> *A retail business sold $2.3M over four years but kept only 12.5% of it as profit. This project finds out where the money is made, and where it quietly leaks away.*

---

## 📑 Table of Contents
1. [Problem Statement](#1-problem-statement)
2. [Headline Findings](#2-headline-findings)
3. [Dataset](#3-dataset)
4. [Tools Used](#4-tools-used)
5. [Data Cleaning & Preparation](#5-data-cleaning--preparation)
6. [Pivot Tables & Charts](#6-pivot-tables--charts)
7. [KPIs](#7-kpis)
8. [Key Insights](#8-key-insights)
9. [Recommendations](#9-recommendations)
10. [Repository Contents](#10-repository-contents)
11. [Limitations & Next Steps](#11-limitations--next-steps)
12. [What I Learned](#12-what-i-learned)

---

## 1. Problem Statement

A retail business wants to understand its sales performance and decide where to focus to grow faster. This analysis answers five questions, each one shown as a banner on the dashboard:

| # | Business question | Dashboard banner |
|---|---|---|
| 1 | How does revenue change over time? | *When do we sell the most?* |
| 2 | Which categories and sub-categories are the most valuable, in sales **and** profit? | *Which categories really earn?* |
| 3 | Which regions perform best and worst? | *Which regions lead?* |
| 4 | Which products generate the most revenue? | *Our top 10 champions* |
| 5 | Do discounts help or hurt profit? | *When do discounts start to hurt?* |

---

## 2. Headline Findings

- 💰 **$2.30M** in sales and **$286K** profit across **5,009 orders**, a **12.5%** profit margin.
- 📉 **Discounts above 20% lose money.** Average profit per order line is **+$67** at 0% discount but **−$78** at 21–40% and **−$107** at 41%+.
- 🪑 **Furniture sells $742K but earns only $18K** (2.5% margin). Tables and Bookcases lose money.
- 🌎 **West is the star region** (14.9% margin). **Central is the weak spot** (7.9% margin) despite selling more than South.
- 📈 **Sales grew about 51% from 2014 to 2017**, with a recurring late-year peak.

---

## 3. Dataset

- **Name:** Superstore Sales Dataset (Kaggle)
- **Source:** https://www.kaggle.com/datasets/vivek468/superstore-dataset-final
- **Contents:** Order-level sales records: order date, region, category, sub-category, product, sales, quantity, discount and profit.
- **Period covered:** January 2014 – December 2017
- **Size:** 9,994 order lines (5,009 unique orders)

---

## 4. Tools Used

| Tool | Purpose |
|---|---|
| Microsoft Excel (Excel for the web) | Data cleaning, PivotTables, charts, dashboard |
| GitHub | Documentation and portfolio |

---

## 5. Data Cleaning & Preparation

1. Kept an untouched copy of the original data on a sheet named **Raw Data**, and did all work on a duplicate sheet named **Clean Data**.
2. Converted the data range into an Excel Table named **Sales**, so every pivot updates from a single source.
3. Ran **Remove Duplicates** across all columns. No duplicate rows were found.
4. Verified that **Order Date** and **Ship Date** are stored as real dates, not text.
5. Checked for blank cells. None were found in the analysis columns.
6. Added helper columns:
   - **Year**: extracted from Order Date
   - **Month**: formatted as `yyyy-mm` for monthly trend analysis
   - **Profit Margin**: Profit ÷ Sales
   - **Discount Band**: groups discounts into 0%, 1–20%, 21–40% and 41%+
7. Added a **Checks** sheet to confirm that the pivot totals match the cleaned data.

---

## 6. Pivot Tables & Charts

All pivot tables are built from the `Sales` table so they include the helper columns.

| Sheet | Rows | Values | Chart |
|---|---|---|---|
| Trend | Month | Sum of Sales | Line: *Monthly Sales, 2014–2017* |
| Products | Product Name (top 10) | Sum of Sales | Bar: *Top 10 Products by Sales* |
| Categories | Category | Sum of Sales, Sum of Profit | Clustered column: *Sales and Profit by Category* |
| Categories (2nd pivot) | Sub-Category (worst to best) | Sum of Profit | Bar: *Profit by Sub-Category* |
| Regions | Region | Sum of Sales, Sum of Profit, Profit Margin | Clustered column: *Sales and Profit by Region* |
| Discounts | Discount Band | Average of Profit | Column: *Average Profit by Discount Band* |

---

## 7. KPIs

| KPI | Value |
|---|---|
| Total Sales | **$2,297,201** |
| Total Profit | **$286,397** |
| Overall Profit Margin | **12.5%** (Total Profit ÷ Total Sales) |
| Number of Orders | **5,009** (unique Order IDs) |
| Average Order Value | **$459** (Total Sales ÷ Orders) |

---

## 8. Key Insights

### 1️⃣ Revenue grows year after year, and peaks late in the year
Yearly sales were about **$484K (2014)**, **$471K (2015)**, **$609K (2016)** and **$733K (2017)**. After a small dip in 2015, growth was strong: roughly **+29%** in 2016 and **+20%** in 2017. Within each year, sales are weakest in the first months (January–February) and climb toward a peak in the final months, with the highest month, **November 2017**, reaching about **$118K**.

### 2️⃣ One product stands out
The **Canon imageCLASS 2200 Advanced Copier** is the top seller at about **$61,600**, more than double the runner-up (about $27,450). Three **GBC binding machines** also appear in the top 10, each with similar sales (about $18,000–$19,800). Revenue is concentrated in office technology.

### 3️⃣ Furniture sells a lot but earns very little
| Category | Sales | Profit | Margin |
|---|---|---|---|
| Technology | ~$836K | ~$145K | ~17.4% |
| Furniture | ~$742K | ~$18K | ~2.5% |
| Office Supplies | ~$719K | ~$122K | ~17.0% |

**Technology** has the highest sales and profit. **Furniture** is second in sales but its profit is tiny because three sub-categories lose money: **Tables (about −$17,700)**, **Bookcases (about −$3,500)** and **Supplies (about −$1,200)**.

Discounts are part of the story but not all of it. Tables (average discount about 26%) and Bookcases (about 21%) are among the most discounted sub-categories, and within Furniture the ranking by discount matches the ranking by profit. However, **Binders have the highest average discount (about 37%) and still make a profit**, while **Supplies lose money with only about 8% average discount**. So other factors, such as product cost and pricing, also matter.

### 4️⃣ West leads; Central lags
**West** has the highest sales (about **$725K**), the highest profit (about **$108K**) and the best margin (**14.9%**). **Central** has the lowest margin (**7.9%**) and the lowest profit (about **$39.7K**), even though its sales (about $501K) are higher than South's (about $392K). Central also has the **highest average discount of the four regions**. This is a link with the low margin, **not proof of cause**.

### 5️⃣ Discounts above 20% lose money
Average profit per order line falls steadily as discounts rise:

| Discount band | Average profit per order line |
|---|---|
| 0% | about **+$67** |
| 1–20% | about **+$27** |
| 21–40% | about **−$78** |
| 41%+ | about **−$107** |

About **1,393 of 9,994 order lines (roughly 14%)** are discounted above 20%. These orders add to sales but reduce profit.

---

## 9. Recommendations

1. **Cap discounts at 20%.** Anything above that loses money on average. Require manager approval for exceptions, and track the 14% of order lines currently above the cap.
2. **Fix Furniture before growing it.** Review pricing, supplier cost and discounts for **Tables** and **Bookcases**, the two biggest losers. Consider raising prices or dropping the worst-performing products.
3. **Invest in Technology and Office Supplies.** Both earn margins of about 17%. Give them more promotion and stock, and protect the top-selling Canon copier from stock-outs.
4. **Investigate Central.** It sells well but keeps the least profit. Review its discounting, product mix and costs, and use **West** as the benchmark.
5. **Plan for the late-year peak.** Prepare stock and promotions ahead of the busy season, and use the slow early months for clearance and planning.

---

## 10. Repository Contents

| File | Description |
|---|---|
| `Superstore_Analysis.xlsx` | Cleaned data, pivot tables and dashboard |
| `dashboard.png` | Screenshot of the final dashboard |
| `README.md` | Project documentation |

---

## 11. Limitations & Next Steps

- This analysis shows **associations, not proven causes**. For example, Central's high discounts go with its low margin, but other factors may contribute.
- Profit is measured per **order line**. Averages can hide a small number of very large losses.
- **Next steps:** add interactive slicers (Region, Category, Year), or rebuild the dashboard in **Power BI**; add units sold (Sum of Quantity) to separate product popularity from high prices.

---

## 12. What I Learned

I started this internship with no data skills. Along the way I learned to **clean and structure data** in Excel, build **PivotTables** and **KPIs**, and design a dashboard that answers specific business questions. The most valuable lesson was that **a good chart is not enough**: the real work is turning numbers into a clear insight and a recommendation a business owner could act on.

---

*Completed as part of the Future Interns Data Science & Analytics internship.*
