# Customer Churn — Data Quality and Exploratory Analysis

## Files
- `churn_analysis.ipynb` — reproducible profiling, cleaning, validation, summary statistics and EDA.
- `cleaned_customer_churn.csv` — cleaned analysis-ready data.
- `data_quality_summary.pdf` — concise audit decisions, checks, findings and limitations.
- `customer_churn_sample.csv` — original supplied dataset (include this file in the repository to make the notebook reproducible).

## Dataset overview
- Rows: 15
- Columns: 11
- Churned customers: 7
- Observed churn rate: 46.7%

## Run the notebook
1. Install Python 3 and Jupyter.
2. Install dependencies: `pip install pandas numpy matplotlib jupyter`
3. Place `customer_churn_sample.csv` beside `churn_analysis.ipynb`.
4. Open Jupyter and choose **Run All**.

## Key data-quality decisions
- Trim text whitespace and explicitly convert numeric columns.
- No missing values, exact duplicate rows, or duplicate customer IDs were found.
- No numeric IQR outliers were flagged.
- `TotalCharges` equals `MonthlyCharges × TenureMonths` for every row within 0.01.
- All records are retained; no unsupported imputation or deletion was performed.

## Initial observations
- Churn: 7/15 (46.7%).
- All Month-to-Month customers in this small sample churned; no One Year or Two Year customers churned.
- Mean support tickets: 4.29 for churned vs 1.00 for retained customers.
- Mean tenure: 7.00 months for churned vs 29.12 months for retained customers.

## Limitations
This is a 15-row synthetic teaching dataset. Findings are descriptive, not causal or statistically generalizable.
