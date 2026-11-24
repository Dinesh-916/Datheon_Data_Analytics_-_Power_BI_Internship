# Task 2: Interactive Power BI Executive Sales Dashboard

**Internship:** Datheon Data Analytics & Power BI Internship  
**Application ID:** DT-2026-KG3SS  
**Difficulty:** Beginner / Intermediate  
**Tools Used:** Power BI Desktop, Power Query (M), DAX  

---

## 📌 Objective
Transform raw corporate **Sample Superstore** sales records into an interactive, multi-visual executive dashboard featuring KPI scorecards, dynamic date and region slicers, category breakdown treemaps, and product profitability matrices to support data-driven leadership decisions.

---

## ⭐ Star Schema Data Model
To optimize query performance and enable accurate time-intelligence calculations, the flat transactional CSV dataset was normalized in Power Query into a **Star Schema**:

* **`Fact_Orders` (Fact Table):** Stores transactional metrics (`Sales`, `Profit`, `Quantity`, `Discount`) connected via one-to-many (`1:*`) relationships to dimension tables using `Order ID`, `Customer ID`, `Product ID`, and `Order Date`.
* **`Dim_Customer` (Dimension Table):** Deduplicated customer profiles (`Customer ID`, `Customer Name`, `Segment`) and geographic hierarchy (`Country` > `Region` > `State` > `City` > `Postal Code`).
* **`Dim_Product` (Dimension Table):** Deduplicated product catalog organized by hierarchy (`Category` > `Sub-Category` > `Product Name`).
* **`Dim_Date` (Dimension Table):** Continuous calendar table generated via `CALENDARAUTO()` and marked as an official Date Table (`Date`, `Year`, `Quarter`, `Month Number`, `Month Name`, `Year-Month`).

---

## 📐 Core DAX Measures
All key business metrics are centralized inside a dedicated `_Measures` table:

```dax
Total Sales = SUM(Fact_Orders[Sales])

Total Profit = SUM(Fact_Orders[Profit])

Total Orders = DISTINCTCOUNT(Fact_Orders[Order ID])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

PY Sales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]))

YoY Sales Growth % = DIVIDE([Total Sales] - [PY Sales], [PY Sales], 0)
```

---

## 📊 Dashboard Visuals & Interactivity
1. **Executive KPI Scorecards:** High-level summary cards tracking **Total Sales**, **Total Profit**, **Profit Margin %**, **Total Orders**, and **YoY Sales Growth %**.
2. **Monthly Sales & Profit Velocity:** Time-series line and waterfall analysis revealing recurring Q4 seasonal revenue surges (September–December).
3. **Category & Sub-Category Treemap:** Hierarchical breakdown sized by `Total Sales` and color-saturated by `Profit Margin %` to highlight top revenue drivers (`Technology`) versus margin laggards (`Furniture`).
4. **Regional Performance Comparison:** Clustered bar chart comparing revenue and net profit across `West`, `East`, `Central`, and `South` regions.
5. **Product Profitability Matrix:** Interactive drill-down matrix with conditional formatting flagging negative-margin sub-categories (`Tables`, `Bookcases`, `Supplies`) caused by aggressive discounting.
6. **Dynamic Slicers:** Interactive page-level filters for `Order Year`, `Region`, `Customer Segment`, and `Ship Mode`.

---

## 💡 Key Executive Insights
* **High-Margin vs. High-Volume Categories:** `Technology` yields the highest profit margin (`~17.4%`), whereas `Furniture` suffers severe margin compression (`~2.5%`) driven by heavily discounted `Tables` and `Bookcases`.
* **Regional Margin Disparity:** `West` and `East` generate over **68%** of total company profit, while the `Central` region underperforms due to frequent `50%–80%` promotional discounts.
* **Seasonal Demand Planning:** Monthly revenue consistently peaks in **November and December**, requiring proactive Q3 inventory allocation for top-performing sub-categories (`Phones`, `Chairs`, `Storage`).

---

## 📂 Files in This Folder
* `Executive_Sales_Dashboard.pbix` — Interactive Power BI Desktop report file with Star Schema model and DAX measures.
* `Executive_Sales_Dashboard.pdf` — High-resolution executive dashboard PDF export.
* `README.md` — Documentation of data architecture, DAX formulas, and analytical findings.
