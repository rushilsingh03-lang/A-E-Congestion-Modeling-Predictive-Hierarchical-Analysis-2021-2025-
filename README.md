Overview

This project analyzes and predicts A&E 4-hour breach performance across NHS trusts between 2021 and 2025. Using a time-aware machine learning pipeline and hierarchical statistical modeling, the goal was to identify the key structural drivers of emergency department congestion and evaluate predictive performance under realistic deployment conditions.

The analysis combines predictive modeling with statistical rigor to move beyond forecasting toward system-level insight.

🎯 Objectives

Predict A&E 4-hour breach percentage using historical trust-level data

Compare multiple model families under a time-based train–test split

Identify key drivers of congestion

Account for hierarchical structure across NHS trusts

Provide interpretable, operationally meaningful insights

🧠 Methodology
1️⃣ Data Preparation

Cleaned trust-level NHS A&E data (2021–2025)

Removed aggregate “TOTAL” rows

Engineered key features:

Emergency_Rate

Waited_12hr_Rate

Log_Total_Attendances

Created target variable: Over4hr_Percentage

2️⃣ Temporal Validation Strategy

Train: 2021–2023

Test: 2024–2025

Preserves real-world forecasting conditions

Prevents data leakage

3️⃣ Models Compared

Linear Regression

Ridge & Lasso

Random Forest

Gradient Boosting

Neural Network (MLP)

Hyperparameter tuning and cross-validation were applied where appropriate.

📊 Results
Model	Test R²	RMSE
Linear / Regularized	~0.80	~6.52
Gradient Boosting	0.83	6.15
Neural Network	0.82	6.21
Random Forest	0.85	5.71

Random Forest achieved the strongest generalization performance, indicating meaningful nonlinear structure in A&E congestion dynamics.

🔎 Key Findings

Emergency admission rate is the dominant driver (~83% feature importance).

Prolonged 12-hour admission waits significantly contribute to congestion.

Raw attendance volume plays a comparatively smaller role.

Mixed-effects modeling revealed substantial baseline variation across trusts.

Interaction testing did not show significant amplification effects between severity and volume.

These results suggest that A&E congestion is primarily driven by admission pressure and downstream bed capacity constraints rather than sheer demand volume.

📐 Advanced Statistical Layer

To account for clustering within trusts, a multilevel mixed-effects model was implemented:

Confirmed significant between-trust heterogeneity

Demonstrated improved model fit compared to standard OLS

Highlighted differences between cross-sectional and within-trust effects

This ensures both predictive strength and statistical robustness.

🛠 Tools & Libraries

Python

pandas / numpy

scikit-learn

statsmodels

matplotlib

🚀 Skills Demonstrated

Time-aware train–test validation

Feature engineering

Hyperparameter tuning

Model comparison across ML families

Interpretability analysis

Multilevel (hierarchical) modeling

Healthcare systems analytics

📌 Conclusion

This project demonstrates an end-to-end data science workflow applied to real-world healthcare performance data. By combining machine learning with hierarchical statistical modeling, it delivers both strong predictive accuracy and actionable system-level insights into the structural drivers of A&E congestion.
