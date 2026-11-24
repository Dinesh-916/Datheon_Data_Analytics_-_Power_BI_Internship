# Datheon_Data_Analytics_-_Power_BI_Internship
End-to-end Data Analytics &amp; Power BI Internship portfolio featuring Python exploratory data analysis, Star Schema data modeling, DAX measures, and executive BI dashboards.

![Status](https://shields.io)
![Application ID](https://shields.io)
![Tech Stack](https://shields.io)

**Intern:** Poreddy Dinesh Reddy
**Institution:**  (Batch 01)  
**Application ID:** `DT-2026`  
**Program Duration:** 4 Weeks (Nov 24, 2026 – Dec 22, 2026)  

---

## 📌 Program Overview
End-to-end Data Analytics and Business Intelligence portfolio developed for the **Datheon Data Analytics & Power BI Internship**. This repository demonstrates corporate data wrangling, exploratory data analysis (EDA), Star Schema data modeling, DAX time-intelligence measures, customer cohort churn analytics, and financial What-If scenario forecasting across four industry-modeled deliverables.

---

## 🗂️ Completed Tasks Summary

| Task | Deliverable Title | Difficulty | Tools & Stack | Status | Folder |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Task 1** | Exploratory Data Analysis (EDA) on Superstore Retail Sales | Beginner | Python (`Pandas`, `Matplotlib`, `Seaborn`), Jupyter | ✅ Completed | [`/Task_1`](./Task_1) |
| **Task 2** | Interactive Power BI Executive Sales Dashboard | Beginner / Interm. | Power BI Desktop, Power Query, DAX (`Star Schema`) | ✅ Completed | [`/Task_2`](./Task_2) |
| **Task 3** | Customer Cohort Retention & Churn Analytics (IBM Telco) | Intermediate | Python (`Pandas`, `NumPy`, `Seaborn`), Jupyter | ✅ Completed | [`/Task_3`](./Task_3) |
| **Task 4** | Corporate Financial Telemetry & Scenario Modeling | Interm. / Advanced | Power BI Desktop, DAX, What-If Parameters | ✅ Completed | [`/Task_4`](./Task_4) |

---

## 📁 Repository Architecture

```text
Datheon_Data_Analytics_&_Power_BI_Internship/
├── data/
│   ├── Sample - Superstore.csv
│   ├── Superstore_Cleaned.csv
│   ├── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   └── Financial Sample.csv
├── Task_1/
│   ├── task1_superstore_eda.ipynb
│   └── README.md
├── Task_2/
│   ├── Executive_Sales_Dashboard.pbix
│   ├── Executive_Sales_Dashboard.pdf
│   └── README.md
├── Task_3/
│   ├── task3_telco_churn_analysis.ipynb
│   ├── Task3_Telco_Churn_Analysis_Report.pdf
│   ├── cohort_retention_heatmap.png
│   ├── high_risk_service_churn.png
│   └── README.md
├── Task_4/
│   ├── Corporate_Financial_Dashboard.pbix
│   ├── Corporate_Financial_Dashboard_Report.docx
│   └── README.md
└── README.md
```

---

## 🔍 Executive Highlights Across All 4 Deliverables

### 1. Task 1 — Superstore Retail Sales EDA (`/Task_1`)
* **Data Wrangling:** Resolved `latin1` encoding characters, imputed missing Burlington, VT postal codes (`05401`), removed exact duplicate transaction rows, and engineered `Year-Month` and `Profit Margin %` metrics.
* **Key Findings:** Identified severe profit margin erosion on discounts exceeding **20%**, strong Q4 seasonal sales spikes (September–December), and high profitability in **Technology** compared to margin drag in **Furniture** (`Tables` and `Bookcases`).

### 2. Task 2 — Interactive Power BI Executive Sales Dashboard (`/Task_2`)
* **Star Schema Modeling:** Normalized flat Superstore records into `Fact_Orders`, `Dim_Customer`, `Dim_Product`, and a continuous `Dim_Date` calendar table.
* **Core DAX Measures:** Built `[Total Sales]` (`$2.30M`), `[Total Profit]` (`$286.40K`), `[Profit Margin %]` (`12.47%`), `[Total Orders]` (`5,009`), and `[YoY Sales Growth %]` (`+20.4%`) powering interactive KPI cards, category treemaps, and regional performance matrices.

### 3. Task 3 — Customer Cohort Retention & Churn Analytics (`/Task_3`)
* **Baseline Benchmark:** Audited **7,043** IBM Telco customers (imputing 11 zero-tenure `TotalCharges` records) and established a baseline churn rate of **26.54%** (**73.46%** retention).
* **Risk Segmentation:** Discovered that `0–12 Month` tenure customers on **Month-to-Month** contracts churn at **51.35%**, **Fiber Optic** users without **Tech Support** churn at **49.37%** (vs. **22.63%** with Tech Support), and **Electronic Check** users churn at **45.29%**.

### 4. Task 4 — Corporate Financial Telemetry & Scenario Modeling (`/Task_4`)
* **P&L Revenue Erosion Bridge:** Modeled **Gross Sales** (`$127.93M`) through **Discounts** (`-$9.21M`) to **Net Sales** (`$118.73M`), and manufacturing **COGS** (`-$101.83M`) down to **Net Profit** (`$16.89M`, **14.23%** gross margin).
* **Variance & What-If Forecasting:** Highlighted **Government** (`21.69%` margin) and **Channel Partners** (`82.39%` margin) versus **Enterprise** net losses (`-$614.55K` under Medium/High discounts), and built interactive **Price Change %** and **COGS Change %** simulation sliders.

---

## 🚀 How to Reproduce Locally

```bash
# 1. Clone the repository
git clone https://github.com<your-username>/Datheon_Data_Analytics_-_Power_BI_Internship.git
cd Datheon_Data_Analytics_-_Power_BI_Internship

# 2. Install Python dependencies for Task 1 & Task 3
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch Jupyter Notebook
jupyter notebook
```

For **Task 2** and **Task 4**, open the `.pbix` files in **Microsoft Power BI Desktop** or review the exported `.pdf` and `.docx` executive reports directly inside each task folder.
