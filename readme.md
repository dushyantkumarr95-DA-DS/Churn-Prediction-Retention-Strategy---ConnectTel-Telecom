# Customer Churn Prediction & Retention Strategy - ConnectTel Telecom

A full end-to-end machine learning project to predict customer churn and design data-driven retention strategies for a pan-India telecom operator.

---

## Business Problem

**ConnectTel Communications Ltd**, a pan-India telecom operator, is experiencing a significant increase in customer churn. The existing approach is reactive: customer are engaged *after* they initiate port-out, disconnection request. This project buils a proactive, data-driven solution.

---

## Objective

1. Accurately identify customers at high risk of churn.
2. Diagnose key behavioral and service-quality drivers of churn.
3. Enable targeted retention strategy to protect revenue.

---

## Dataset

| Property | Detail |
|----------|--------|
| Records| 25,000 unique customers |
| Features | 36 columns |
| Target | 'is_churn' (binary:1 = churned) |
| Churn Rate | ~41% |

Feature categories include customer demographics, plan, usage & billing behavior, network quality, payment behavior, and customer sentiment signals.

---

## Project Workflow

1. **Data Loading & Quality Checks** - duplicates, missing values, logical consistency.
2. **Exploratory Data Analysis (EDA)** - distribution analysis, outlier detection, churn analysis by segment.
3. **Feature Engineering** - derived behavioral, lifecycle, customer satisfaction features.
4. **Preprocessing** - One-Hot Encoding, Robust Scaling.
5. **Model Training** - Logistic Regression, Random Forest, XGBoost.
6. **Threshold Tuning** - optimized decision boundary for recall.
7. **Segment-Based Targetting** - Top-N probability strategy for high-value customers.
8. **Business Impact Quantification** - revenue at risk & recoverable revenue estimation.

---

## Models & Results

| Model | ROC-AUC | Recall(Churn) | Precison(Churn) | F1-Score |
|-------|---------|---------------|-----------------|----------|
| Logistic Regression Baseline | 0.661 | 0.58 | 0.54 | 0.56 |
| Logistic Regression Tuned | **0.66** | **0.61** | 0.53 | 0.57 |
| Random Forest with Feature Engineering | 0.64 | 0.56 | 0.52 | 0.54 |
| Random Forest without Feature Engineering | 0.64 | 0.64 | 0.50 | 0.56 |
| XG Boost | 0.65 | 0.58 | 0.52 | 0.55 |

> **Selected Model**: Tuned Logistic Regression - best balance of churn recall and retention strategy.

---

## Business Impact

| Metric | Value |
|--------|-------|
| Total churned customers | 10357 |
| Annual revenue at risk | ₹5.59 Crore |
| Customers identified by model | 6317 (61% recall) |
| Customers retained(35% success rate assumed) | 2210 |
| **Estimated revenue saved** | **₹1.19 Crore/year** |
| Revenue risk mitigated | 21% |

### High-Value Segment - Top-N targeting

| Target Group | Chirn Rate |
|--------------|------------|
| All high-value customers(baseline) | 31% |
| Top 30% by churn probability | **43%** |
| Top 50% by vhurn probability | 37% |

---

## Key Insights

**Churn Drivers:**
- Exposure to competitor offers (strongest signals)
- New customers (tenure ≤ 12 months)
- Prepaid plan users
- Low NPS scores & frequent complaints
- High complaint resolution time

**Retention Drivers:**
- High service ratings and NPS
- Postpaid plan & long-term contracts
- Long tenure

---

## 🛠️ Tech Stack

**Python**, **Pandas**, **Scikit-learn**, **XG Boost**, **Seaborn**, **Matplotlib**

- **Data Manipulation:** Pandas, Numpy
- **Visualization:** Matplotlib, Seaborn
- **Preprocessing:** OneHotEncoder, RobustScaler
- **ML Models:** Scikit-learn, XGBoost
- **Model Persistence:** Joblib

---
