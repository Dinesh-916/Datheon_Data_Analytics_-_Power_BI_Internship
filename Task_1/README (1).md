# Data Analytics & Power BI Internship — Datheon

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-EDA-150458)
![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811)
![Status](https://img.shields.io/badge/Status-In%20Progress-success)

**Application ID:** `DT-2026-KG3SS`  
**Track:** Data Analytics & Power BI Internship (4-Week Cadence)  

---

## 📌 Project Overview
This repository contains end-to-end business intelligence deliverables transforming corporate retail sales data (**Sample Superstore**) into cleaned analytical datasets, exploratory insights, and executive Power BI dashboards.

### Repository Architecture
```text
datheon-data-analytics-internship/
├── data/
│   ├── Sample - Superstore.csv       # Raw corporate retail dataset
│   └── Superstore_Cleaned.csv        # Wrangled & validated dataset for BI modeling
├── notebooks/
│   └── task1_superstore_eda.ipynb    # Python EDA, statistical profiling & visualizations
├── dashboards/
│   └── Superstore_Sales_Report.pbix  # Interactive Power BI Executive Dashboard (Task 2)
└── README.md                         # Project documentation & business findings
```

---

## ✅ Completed Tasks & Deliverables

### Task 1: Exploratory Data Analysis (EDA) on Superstore Retail Sales
* **Objective:** Execute data wrangling, missing-value profiling, commercial sales distribution analysis, and discount sensitivity modeling.
* **Tools Used:** Python (`Pandas`, `NumPy`, `Matplotlib`, `Seaborn`), Jupyter Notebook.
* **Data Cleaning Actions:**
  * Imputed missing `Postal Code` records for Burlington, VT (`05401`) and standardized all ZIP codes as 5-digit zero-padded strings.
  * Identified and removed exact duplicate transaction rows (e.g., duplicate order lines on `US-2015-150119`).
  * Parsed `Order Date` and `Ship Date` fields to engineer `Year-Month` time series and `Profit Margin %` metrics.

#### Key Executive Findings (Task 1)
1. **Category Margin Divergence:** **Technology** drives the highest profit margins, while **Furniture** (specifically *Tables* and *Bookcases*) suffers net losses under promotional pricing.
2. **Discount Erosion Cliff:** Discounts up to **20%** preserve positive profitability; discounts of **30% to 80%** sharply erode margins and generate severe negative profit outliers.
3. **Q4 Seasonal Surges:** Revenue accelerates consistently from **September through December**, highlighting peak corporate year-end and holiday demand.
4. **Segment Volume Concentration:** The **Consumer** segment represents the largest share of transaction volume, supported by steady high-value orders from **Corporate** buyers.
5. **Regional Performance Gap:** **West** and **East** regions lead net profit generation, while the **Central** region lags due to heavy discounting on *Binders* and *Appliances*.

---

### Task 2: Interactive Power BI Executive Dashboard *(Upcoming / In Progress)*
* **Objective:** Build a multi-page interactive executive dashboard using a **Star Schema** data model (`Fact_Orders`, `Dim_Customer`, `Dim_Product`, `Dim_Date`) and custom **DAX measures** (Total Sales, Total Profit, Profit Margin %, YoY Growth).

---

## 🚀 How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-username>/datheon-data-analytics-internship.git
   cd datheon-data-analytics-internship
   ```

2. **Install Python dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook notebooks/task1_superstore_eda.ipynb
   ```
