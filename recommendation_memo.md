# Recommendation Memo: Customer Segmentation & Churn-Risk Prioritisation

## Decision question
Which customers should a retention team review first, and what proportionate action should it consider?

## Dataset and approach
The analysis uses 15 synthetic customer records. Four transparent signals form an additive rule-based score. The observed `Churn` outcome is deliberately excluded from the score and segment assignment; it is used only after scoring for a descriptive validation check.

## Rule-based score (0–8 points)
| Signal | Points |
|---|---:|
| Month-to-Month contract | +3 |
| Tenure of 12 months or less | +2 |
| At least 4 support tickets | +2 |
| Monthly charges of at least ₹80 | +1 |

Risk tiers: Low = 0–2; Medium = 3–4; High = 5–8. The thresholds are transparent operational rules for this teaching exercise, not statistically calibrated probabilities.

## Customer segments
1. **New & High Support:** tenure ≤12 months AND support tickets ≥4.
2. **Month-to-Month Watchlist:** Month-to-Month contract, excluding customers already in New & High Support.
3. **Established & Stable:** tenure >24 months AND support tickets ≤2 AND not Month-to-Month.
4. **Developing Customers:** all remaining records.

The rules are evaluated in the order above, so every customer belongs to exactly one segment.

## Recommended actions
- **New & High Support:** proactive service recovery, resolve issues, and provide onboarding help. Do not assume a discount is the right fix.
- **Month-to-Month Watchlist:** understand why the customer remains monthly; explain annual-plan value and consider a voluntary incentive where appropriate.
- **Established & Stable:** maintain service quality and recognise loyalty; avoid unnecessary discounting.
- **Developing Customers:** conduct a short satisfaction check-in and monitor service signals.

## Validation and observed pattern
- Records scored: 15.
- Risk-tier counts: {'Low': 8, 'High': 6, 'Medium': 1}.
- Segment counts: {'New & High Support': 5, 'Developing Customers': 4, 'Established & Stable': 4, 'Month-to-Month Watchlist': 2}.
- Observed churn labels are shown in the customer-level CSV only for a post-hoc descriptive comparison; they do not contribute to points or segment labels.

## Edge cases tested
- Tenure exactly 12 months receives the ≤12-month points and qualifies for the New & High Support segment if support tickets are also ≥4.
- Tenure 13 months does not receive the short-tenure points.
- Exactly 4 support tickets receives the support points.
- Exactly ₹80 monthly charges receives the charge points.
- Risk score 2 is Low; 3 and 4 are Medium; 5 is High.
- Missing required feature values or invalid negative tenure/support-ticket values should fail validation rather than silently become zero.

## Limitations
This is a tiny synthetic sample (15 records). The score is not a machine-learning model, probability, or proven predictor of future churn. Rules and thresholds are illustrative and should be calibrated on a larger, representative, time-stamped dataset before operational use. The dataset lacks customer feedback, usage trends, complaint severity, competitor offers, and intervention outcomes. Recommendations are hypotheses to test, not guaranteed retention outcomes.
