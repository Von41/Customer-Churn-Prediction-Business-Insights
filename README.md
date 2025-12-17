Customer Churn Prediction (Telecom)
Overview

An end-to-end machine learning project to predict customer churn and identify key drivers of customer attrition using explainable models.

Business Objective

Identify customers likely to churn before they leave, enabling proactive retention actions. Recall is prioritized over accuracy to minimize missed churn cases.

Dataset

⦁	Telco Customer Churn dataset (Kaggle)
⦁	~7,000 customers
⦁	Target: Churn

Approach

⦁	EDA: Identified churn drivers such as tenure, pricing, contract type, and support services
⦁	Feature Engineering: Created tenure buckets, contract length, auto-payment flags, and support aggregates
⦁	Modeling: Logistic Regression (final), Random Forest (benchmark)
⦁	Threshold Tuning: Optimized decision threshold to improve churn recall
⦁	Explainability: Logistic coefficients + SHAP (global & local)

Key Insights

⦁	Short tenure and high monthly charges increase churn risk
⦁	Long contracts, auto-payment, and support services reduce churn
⦁	Optimized threshold captures ~86% of potential churners

Tech Stack

Python, Pandas, NumPy, Scikit-learn, SHAP, Matplotlib, Seaborn

Repository Structure:
  notebooks/
    01_eda.ipynb
    02_feature_engineering.ipynb
    03_modeling.ipynb
    04_explainability.ipynb
  models/
    final_churn_model.pkl
