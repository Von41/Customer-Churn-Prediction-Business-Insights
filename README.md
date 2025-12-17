# Customer Churn Prediction (Telecom)

## Overview
End-to-end machine learning project to predict customer churn and identify key churn drivers using interpretable models.

The focus is on **early identification of customers likely to churn**, enabling proactive retention strategies.

---

## Dataset
- Telco Customer Churn Dataset (Kaggle)
- ~7,000 customers
- Target: `Churn`

---

## Approach
- **EDA:** Identified churn drivers such as tenure, pricing, contract type, and support services  
- **Feature Engineering:** Tenure buckets, contract length, auto-payment flag, support aggregation  
- **Modeling:** Logistic Regression (final), Random Forest (benchmark)  
- **Threshold Tuning:** Optimized threshold (0.40) to improve churn recall  
- **Explainability:** Logistic coefficients and SHAP (global & local)

---

## Key Insights
- Short tenure and high monthly charges increase churn risk  
- Long contracts, auto-payment, and support services reduce churn  
- Optimized threshold captures ~86% of potential churners  

---

## Tech Stack
Python, Pandas, NumPy, Scikit-learn, SHAP, Matplotlib, Seaborn

---
---

## Repository Structure
- telco-churn-prediction/
- ├── data/
- │ ├── raw/
- │ └── processed/
- ├── notebooks/
- │ ├── 01_eda.ipynb
- │ ├── 02_feature_engineering.ipynb
- │ ├── 03_modeling.ipynb
- │ └── 04_explainability.ipynb
- ├── models/
- │ └── final_churn_model.pkl
- ├── requirements.txt
- └── README.md