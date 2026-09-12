# Customer Churn Analysis

An end-to-end churn analysis project on telecom customer data — from raw data cleaning to SQL business queries, a machine learning prediction model, and an interactive Power BI dashboard.

## Problem Statement

The telecom company needs to identify which customers are likely to churn and why, in order to proactively design retention strategies.

## Tools Used

- **Python** (Pandas, scikit-learn) — data cleaning and churn prediction model
- **SQL** (PostgreSQL) — business question analysis
- **Power BI** — interactive dashboard with what-if analysis

## Process

1. **Data Cleaning** — Handled missing/blank values (e.g. blank `TotalCharges`), fixed data types, and standardized categorical fields.
2. **SQL Analysis** — Wrote business-question queries in PostgreSQL (churn rate by contract type, by tenure group, high-value churned customers, average charges/tenure comparison).
3. **Churn Prediction Model** — Built a Logistic Regression model (scikit-learn) to predict churn probability for each customer.
4. **Power BI Dashboard** — Built an interactive dashboard with KPI cards, a churn split pie chart, and a what-if parameter to explore how churn rate changes with tenure.

## Key Findings

1. **Contract type is the strongest churn driver** — Month-to-month customers churn at **42.6%**, compared to 11.3% for one-year and just 2.8% for two-year contracts. The company should incentivise longer contracts through loyalty discounts or bundled offers to reduce churn and make revenue more predictable.

2. **Churn risk is highest in the first year** — Customers with 0–12 months tenure churn at **47.4%**, dropping to 28.7% (13–24 months) and 14.0% (25+ months). Improving early onboarding — welcome calls, first-90-day check-ins, early-loyalty rewards — could meaningfully reduce this early churn.

3. **High monthly charges correlate with higher churn** — Customers paying $70+/month churn at **35.3%**, versus 10.7% for those paying under $35. High-paying customers should be proactively monitored and offered value-added perks rather than left to churn silently.

4. **Electronic check users are a distinct at-risk segment** — They churn at **45.1%**, far above Credit Card (15.2%), Bank Transfer (16.7%), and Mailed Check (18.9%). Encouraging a switch to automatic payment methods could help lower churn.

5. **Lack of Tech Support strongly predicts churn** — Customers without Tech Support churn at **41.5%** vs. 15.2% for those who have it; Fiber optic users also churn far more (41.8%) than DSL users (18.9%). Bundling free tech support for new customers, especially on Fiber optic plans, could reduce early frustration and churn.

**Overall risk profile:** A new customer, on a month-to-month contract, paying high monthly charges via electronic check, without tech support, is the company's highest-risk segment for churn — a clear target for a retention campaign.


## Repository Structure

```
├── README.md                          # Project overview (this file)
├── notebooks/
│   └── churn_analysis.ipynb           # Data cleaning, EDA, and ML model
├── sql/
│   └── queries.sql                    # Business-question SQL queries
├── dashboard/
│   ├── churn_dashboard.pbix           # Power BI dashboard file
│   └── dashboard_screenshot.png       # Dashboard preview image
└── data/
    ├── cleaned_churn.csv              # Cleaned dataset
    └── churn_predictions.csv          # Model output with churn probabilities
```

## How to Reproduce

1. Clone this repository
2. Open `notebooks/churn_analysis.ipynb` to see the data cleaning and model-building steps
3. Run `sql/queries.sql` against a PostgreSQL database loaded with `cleaned_churn.csv`
4. Open `dashboard/churn_dashboard.pbix` in Power BI Desktop to explore the interactive dashboard
