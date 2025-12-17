#  Customer Churn Prediction (Telecom)

## Overview
An end-to-end machine learning project to predict customer churn and identify key drivers of customer attrition using interpretable and explainable models.

This project focuses on **business-aligned decision-making**, prioritizing early identification of customers likely to churn so that proactive retention actions can be taken.

---

## Business Objective
Identify customers who are **likely to churn in the near future**, enabling proactive retention strategies.

In a churn prevention context:
- Missing a churner is more costly than contacting a loyal customer
- Recall is therefore prioritized over raw accuracy

---

## Dataset
- **Source:** Telco Customer Churn Dataset (Kaggle)
- **Size:** ~7,000 customers
- **Target Variable:** `Churn` (Yes / No)

Features include customer tenure, pricing, contract details, payment behavior, service usage, and demographics.

---

## Approach

### 1. Exploratory Data Analysis (EDA)
- Analyzed churn distribution and class imbalance
- Identified key churn drivers:
  - Short tenure
  - Month-to-month contracts
  - High monthly charges
  - Lack of support services
  - Payment friction
- Performed data quality checks and handled missing values

`01_eda.ipynb`

---

### 2. Feature Engineering
- Created business-driven features:
  - Tenure buckets
  - Contract length encoding
  - Auto-payment indicator
  - Support services aggregation
  - Pricing sensitivity features
- Removed redundant and non-informative columns
- Ensured all features were numeric and model-ready

`02_feature_engineering.ipynb`

---

### 3. Modeling
- Trained and evaluated:
  - Logistic Regression (final model)
  - Random Forest (benchmark)
- Used stratified train–test split
- Evaluation metrics:
  - ROC-AUC
  - Precision, Recall, F1-score

Logistic Regression was selected due to:
- Slightly better ROC-AUC
- Strong interpretability
- Stable performance

`03_modeling.ipynb`

---

### 4. Threshold Optimization
- Evaluated multiple decision thresholds
- Optimized threshold to improve recall
- Final threshold selected: **0.40**

This captures approximately **86% of potential churners** while maintaining a manageable false-positive rate.

`03_modeling.ipynb`

---

### 5. Model Explainability
To ensure transparency and trust:

- **Logistic Regression Coefficients**
  - Identified features increasing and reducing churn risk
- **SHAP Explainability**
  - Global insights using SHAP summary and bar plots
  - Local explanations using SHAP waterfall plots for individual customers

`04_explainability.ipynb`

---

## Key Insights
- Customers with **short tenure and high monthly charges** are most likely to churn
- **Contract length** is one of the strongest churn-reducing factors
- **Auto-payment and support services** significantly reduce churn risk
- Early identification enables effective churn prevention strategies

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- SHAP
- Joblib

---

## Repository Structure
telco-churn-prediction/
├── data/
│ ├── raw/
│ └── processed/
├── notebooks/
│ ├── 01_eda.ipynb
│ ├── 02_feature_engineering.ipynb
│ ├── 03_modeling.ipynb
│ └── 04_explainability.ipynb
├── models/
│ └── final_churn_model.pkl
├── requirements.txt
└── README.md