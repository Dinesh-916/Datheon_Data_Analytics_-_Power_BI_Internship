# Task 3: Customer Cohort Retention & Churn Analytics (IBM Telco)

**Internship:** Datheon Data Analytics & Power BI Internship  
**Application ID:** DT-2026-KG3SS  
**Difficulty:** Intermediate  
**Tools Used:** Python (`Pandas`, `NumPy`, `Matplotlib`, `Seaborn`), Jupyter Notebook  

---

## 📌 Objective
Analyze telecom and SaaS customer retention behavior using the **IBM Telco Customer Churn** dataset (`7,043` customer records). Segment customers by contract vintage, tenure cohorts, internet service tiers, technical support add-ons, and payment methods to compute retention matrices and deliver actionable churn-reduction strategies.

---

## 🧹 Data Quality & Preparation Summary
1. **Dataset Profiling:** Audited **7,043** unique customer records across **21** demographic, account, and service attributes.
2. **Zero-Tenure Imputation:** Identified **11** brand-new customers (`tenure = 0`) with blank string values (`" "`) in `TotalCharges`; coerced `TotalCharges` to numeric and imputed `0.0` to retain all records.
3. **Feature Engineering:** Created binary `Churn_Flag` (`1` = Yes, `0` = No) and binned customer `tenure` into five lifecycle cohorts (`0–12 Mos`, `13–24 Mos`, `25–48 Mos`, `49–60 Mos`, and `61+ Mos`).

---

## 📊 Key Analytical Findings
* **Baseline Churn Benchmark:** Out of **7,043** total customers, **1,869** churned and **5,174** stayed, yielding an overall baseline churn rate of **26.54%** (**73.46%** retention).
* **Contract & Tenure Vulnerability:** New customers (`0–12 Months` tenure) on **Month-to-Month** contracts experience the highest churn probability at **51.35%**, whereas **Two-Year** contract holders maintain **97.17%** retention (`2.83%` churn).
* **Fiber Optic + No Tech Support Risk:** **Fiber Optic** customers without **Tech Support** churn at **49.37%** (nearly double the company average), compared to **22.63%** for Fiber Optic subscribers with active Tech Support.
* **Payment Method Friction:** Customers paying via **Electronic Check** churn at **45.29%**, whereas automated payment methods (**Credit Card** at **15.24%** and **Bank Transfer** at **16.71%**) show dramatically stronger retention.

---

## 🎯 Strategic Retention Recommendations
1. **6-Month Contract Upgrade Campaign:** Target Month-to-Month subscribers at Month 6 with a 10% loyalty discount or complimentary streaming add-on for migrating to a 1-Year agreement.
2. **Complimentary Tech Support Onboarding:** Bundle 6 months of free Tech Support with all new Fiber Optic plans to reduce early-stage service friction.
3. **Auto-Pay Migration Incentive:** Offer a one-time \$10–\$15 bill credit to Electronic Check customers who enroll in automatic Credit Card or Bank Transfer billing.

---

## 📂 Files in This Folder
* `task3_telco_churn_analysis.ipynb` — Complete Jupyter Notebook with data cleaning, cohort matrix, visualizations, and strategic findings.
* `Task3_Telco_Churn_Analysis_Report.pdf` — Executive summary PDF report.
* `cohort_retention_heatmap.png` — Heatmap visualizing customer retention rates across tenure cohorts and contract types.
* `high_risk_service_churn.png` — Bar chart comparing churn probability across internet tiers and technical support plans.
* `README.md` — Documentation of methodology, metrics, and retention strategy.

---

## 🚀 How to Run Locally
```bash
# Install required libraries
pip install pandas numpy matplotlib seaborn jupyter

# Launch Jupyter Notebook
jupyter notebook task3_telco_churn_analysis.ipynb
```
