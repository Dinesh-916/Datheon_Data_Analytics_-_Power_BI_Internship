# Task 4: Corporate Financial Telemetry & Scenario Modeling Dashboard

**Internship:** Datheon Data Analytics & Power BI Internship  
**Application ID:** DT-2026-KG3SS  
**Difficulty:** Intermediate / Advanced  
**Tools Used:** Power BI Desktop, Power Query (M), DAX, What-If Scenario Modeling  

---

## 📌 Objective
Model corporate financial statement telemetry using the **Microsoft Financial Sample** dataset (`700` global manufacturing records across `2013–2014`). Construct income statement hierarchies, revenue erosion waterfall charts, geographic and segment variance matrices, and dynamic What-If scenario forecasting sliders to guide executive pricing and cost decisions.

---

## 🧹 Data Preparation & Model Architecture
1. **Schema Standardization:** Trimmed leading spaces in raw column headers (specifically ` Sales` → `Net Sales`) and enforced currency/decimal types across financial metrics.
2. **Income Statement Hierarchy:** Structured the P&L bridge from **Gross Sales** (`$127.93M`) through **Discounts** (`-$9.21M`) to **Net Sales** (`$118.73M`), and subtracted **Manufacturing COGS** (`-$101.83M`) to arrive at **Net Profit** (`$16.89M`).
3. **Waterfall Bridge Helper Table:** Built a sorted `Waterfall_Bridge` dimension (`Step_Order` 1–5) to render cumulative top-line to bottom-line revenue erosion in Power BI.

---

## 📐 Core DAX Measures & What-If Parameters
All key profitability ratios and dynamic scenario simulations are centralized in a `_Financial_Measures` table:

```dax
Total Gross Sales = SUM(financials[Gross Sales])

Total Discounts = SUM(financials[Discounts])

Net Sales = SUM(financials[Net Sales])

Total COGS = SUM(financials[COGS])

Net Profit = SUM(financials[Net Profit])

Gross Profit % = DIVIDE([Net Profit], [Net Sales], 0)

COGS Ratio = DIVIDE([Total COGS], [Net Sales], 0)

Segment Margin = CALCULATE([Gross Profit %], ALLEXCEPT(financials, financials[Segment]))

Simulated Net Sales = [Net Sales] * (1 + 'Price_Change_Pct'[Price_Change_Pct Value])

Simulated Net Profit = [Simulated Net Sales] - ([Total COGS] * (1 + 'COGS_Change_Pct'[COGS_Change_Pct Value]))

Profit Variance \$ = [Simulated Net Profit] - [Net Profit]
```

---

## 📊 Key Analytical Findings
* **Corporate Profitability Baseline:** Across **$127.93M** in Gross Sales, promotional discounts eroded **$9.21M** (`7.20%` discount rate), yielding **$118.73M** in Net Sales and **$16.89M** in Net Profit (**14.23%** gross margin; **85.77%** COGS ratio).
* **Segment Margin Divergence:**
  * **Government** generates **67.4%** of total company profit (**$11.39M** Net Profit at a **21.69%** margin).
  * **Channel Partners** achieves the highest margin efficiency (**82.39%**) due to low per-unit manufacturing costs relative to channel pricing.
  * **Enterprise** operates at a net loss (**-$614.55K**, **-3.13%** margin) because `Medium` and `High` discount bands (`5%–15%`) push the `$125` Enterprise price below its `$120/unit` manufacturing COGS.
* **Geographic Performance:** **United States** (`$25.03M` Net Sales) and **Canada** (`$24.89M` Net Sales) lead revenue volume, while **France** leads net profit margin at **15.49%**.
* **Scenario Sensitivity:** Modeling a **+5% Price Optimization** alongside a **-3% COGS Reduction** lifts corporate Net Profit from **$16.89M** to **$25.88M** (**+$8.99M** profit variance).

---

## 🎯 Strategic Financial Recommendations
1. **Cap Enterprise Discounting at `Low` (`1%–4%`):** Eliminate `Medium` and `High` discount tiers on Enterprise contracts where unit manufacturing cost (`$120`) leaves insufficient margin buffer.
2. **Expand Government & Small Business Allocation:** Prioritize sales capacity in high-margin Government (`21.69%`) and Small Business (`16.01%`) channels across North America and Europe.
3. **Target Manufacturing COGS Efficiency:** Focus procurement optimization on high-cost product lines (`VTT` at `$250` and `Amarilla` at `$260` manufacturing price) to lower the `85.77%` COGS ratio.

---

## 📂 Files in This Folder
* `Corporate_Financial_Dashboard.pbix` — Interactive Power BI Desktop report with P&L waterfall bridge, variance matrix, and What-If scenario sliders.
* `Corporate_Financial_Dashboard_Report.docx` — Executive financial variance and scenario modeling report with embedded charts.
* `README.md` — Documentation of financial model architecture, DAX formulas, and executive insights.
