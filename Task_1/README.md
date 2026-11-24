# Task 1: Exploratory Data Analysis (EDA) on Superstore Retail Sales

**Internship:** Datheon Data Analytics & Power BI Internship  
**Application ID:** DT-2026-KG3SS  
**Difficulty:** Beginner  
**Tools Used:** Python (`Pandas`, `NumPy`, `Matplotlib`, `Seaborn`), Jupyter Notebook  

---

## 📌 Objective
Perform end-to-end data wrangling, missing-value profiling, and exploratory data analysis on the corporate **Sample Superstore** retail dataset to uncover commercial sales distributions, monthly seasonality, category-wise profitability, and discount sensitivity.

---

## 🧹 Data Cleaning & Preparation Summary
Before conducting statistical analysis, the raw dataset (`Sample - Superstore.csv`) was cleaned and validated through the following steps:
1. **Encoding Standardization:** Loaded the dataset using `latin1` encoding to preserve international customer names (e.g., accented characters).
2. **Missing Value Imputation:** Identified missing `Postal Code` records in Burlington, Vermont, imputed the accurate ZIP code (`05401`), and formatted all postal codes as 5-digit strings to preserve leading zeros.
3. **Duplicate Removal:** Detected and removed exact duplicate transaction rows (excluding unique `Row ID`s) to prevent revenue and profit inflation.
4. **Feature Engineering:** Parsed `Order Date` and `Ship Date` into datetime objects and engineered `Year-Month`, `Order Month`, and `Profit Margin %` metrics.

---

## 📊 Key Analytical Visualizations
* **Monthly Sales & Profit Velocity:** Time-series line chart tracking revenue and profit trends across all order months to identify seasonal peaks.
* **Discount Rate vs. Profit Sensitivity:** Scatter plot segmented by product category illustrating the break-even threshold where discounting erodes net margins.
* **Sub-Category Profitability Ranking:** Horizontal bar chart highlighting top-performing products versus loss-making sub-categories.

---

## 💡 5 Executive Business Takeaways
1. **Technology Drives Margin While Furniture Drags Profitability:** Technology generates the highest profit margin across all categories, whereas Furniture (especially Tables and Bookcases) experiences heavy net losses when discounted.
2. **Severe Margin Erosion Above 20% Discounts:** Transactions with `0%` to `20%` discounts remain consistently profitable, while discounts between `30%` and `80%` cause steep negative profit margins.
3. **Strong Q4 Seasonality:** Order volume and revenue peak sharply every year between September and December, driven by Q4 corporate purchasing and holiday demand.
4. **Consumer Segment Leads Order Volume:** The Consumer segment accounts for roughly half of total order volume, whereas Corporate and Home Office segments yield higher average order values.
5. **Regional Profit Disparity:** The West and East regions lead overall profitability, while the Central region underperforms due to aggressive discounting on office binders and appliances.

---

## 📂 Files in This Folder
* `task1_superstore_eda.ipynb` — Complete Jupyter Notebook with data cleaning pipeline, visualizations, and annotated findings.
* `Sample - Superstore.csv` — Raw corporate retail dataset.
* `Superstore_Cleaned.csv` — Exported clean dataset ready for Power BI modeling (Task 2).

---

## 🚀 How to Run Locally
```bash
# Install required libraries
pip install pandas numpy matplotlib seaborn jupyter

# Launch Jupyter Notebook
jupyter notebook task1_superstore_eda.ipynb
```
