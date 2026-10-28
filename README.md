# Bank-Marketing-Deposit-Prediction

# Bank Marketing: Term Deposit Subscription Prediction

Predicts whether a customer will subscribe to a term deposit after a marketing call, using XGBoost.

## Dataset
- File: `bank.csv`
- 11,162 customers, 16 features + target (`deposit`: yes/no)
- Customer info (age, job, education, balance, loans) and campaign info (contact type, month, number of calls, previous outcome)
- Classes are almost balanced (about 47% subscribed)


## Workflow
1. Data overview and cleaning
2. Exploratory data analysis
3. Encoding and train/test split
4. XGBoost classifier
5. Threshold tuning, confusion matrix, ROC curve and feature importance

## Key Findings
- Students (75%) and retired customers (66%) subscribe the most
- Customers without a housing loan subscribe far more (57% vs 37%)
- Customers who subscribed in a previous campaign say yes 91% of the time
- May has the most calls but the lowest success rate (33%)
- More calls to the same customer lowers the success rate
- `duration` (call length) is dropped from the model because it is only known after the call (data leakage)

## Results
Evaluated on 2,233 test customers at a 0.5 threshold:

| Metric | Score |
| Accuracy | 0.72 |
| Precision | 0.74 |
| Recall | 0.63 |
| F1 | 0.68 |
| ROC-AUC | 0.78 |

#The top predictors are previous campaign success, unknown contact type and the month of contact.

## Tools
Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, XGBoost
