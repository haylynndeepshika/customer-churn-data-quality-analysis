# Business KPI Dashboard — Customer Churn

## Live dashboard
After enabling GitHub Pages, open the repository's Pages URL. The entry page is `index.html`.

## What it contains
- Churn rate and retention rate
- Monthly revenue at risk (INR)
- Average customer tenure
- Interactive filters for contract type, tenure band, and payment method
- Churn split, churn by contract, payment-method breakdown, and tenure comparison charts
- Short observations that update with filters

## KPI definitions
- Churn rate = churned customers / all customers in the selected segment × 100
- Retention rate = retained customers / all customers in the selected segment × 100
- Monthly revenue at risk = sum of monthly charges for customers marked churned in the selected segment
- Average tenure = mean of completed tenure months in the selected segment

Revenue at risk is an exposure proxy based on monthly charges, not a forecast or lifetime revenue estimate.

## Data and limitations
Uses the supplied synthetic 15-customer sample. Results are descriptive and not statistically generalisable. Do not interpret associations as causes.

## Publish with GitHub Pages
1. Upload `index.html`, `dashboard_data.csv`, and this README to the public project repository.
2. Open repository Settings → Pages.
3. Under Build and deployment, choose Deploy from a branch.
4. Choose `main` and `/ (root)`, then Save.
5. Wait for deployment and open the published Pages URL.
