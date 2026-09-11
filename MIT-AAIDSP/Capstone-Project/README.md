# Loan Default Prediction — MIT AAIDSP Capstone Project

![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-Selected%20Model-0b7285)
![Task](https://img.shields.io/badge/Task-Binary%20Classification-purple)

Capstone project for the **MIT Applied AI & Data Science Program (AAIDSP)**. It builds and
evaluates supervised-learning models to predict whether a home-equity loan applicant is likely
to **default**, supporting data-driven credit-risk decisions.

---

## Project Description

Consumer lenders must decide which applicants to approve while managing the risk of default.
This project uses the **HMEQ (Home Equity) dataset** of **5,960 loan applications** to build a
binary classifier that flags applicants likely to default (`BAD = 1`) versus repay (`BAD = 0`).
Because defaults are costly and relatively rare (~20% of applicants), the work emphasises
**recall on the default class**, class-imbalance handling, and model explainability.

## Problem Statement

> **Binary classification problem:** identify which loan applicants are likely to default on a
> home-equity loan, so the bank can support credit-risk decision-making — approving sound
> applicants quickly while flagging high-risk applications for review or rejection.

A false negative (approving a defaulter) is far more expensive than a false positive (declining
a good applicant), so the modelling and threshold choices are tuned to **catch as many
defaulters as possible** without sacrificing overall performance.

## Tech Stack

- **Language:** Python
- **Data & compute:** pandas, numpy
- **Visualisation:** matplotlib, seaborn
- **Modelling:** scikit-learn and XGBoost (nine model variants evaluated)
- **Class imbalance:** imbalanced-learn (**SMOTE**)
- **Explainability:** **SHAP**, permutation importance

## Approach & Workflow

1. **Data inspection** — load HMEQ (5,960 rows, 12 predictors + `BAD` target); assess types and missingness.
2. **Exploratory Data Analysis** — univariate, target, bivariate and multivariate analysis.
3. **Preprocessing** — median/mode imputation with a **missingness flag** (`DEBTINC` is ~21% missing and its absence is itself predictive), IQR winsorization of outliers, feature engineering, and categorical encoding.
4. **Leakage-resistant data partitioning** — stratified training, validation and untouched test sets.
5. **Class imbalance** — **SMOTE applied inside the training pipeline only**, including during cross-validation.
6. **Model building** — nine variants, including logistic regression, tree ensembles and gradient-boosting models.
7. **Hyperparameter tuning** — stratified cross-validation with preprocessing and resampling refitted within each fold.
8. **Model comparison & selection** — validation Average Precision and ROC-AUC used alongside default-class recall, precision and F1.
9. **Feature importance & explainability** — model importance, permutation importance and **SHAP**, with explicit governance limitations.
10. **Threshold optimisation** — threshold selected on validation data, locked, and then evaluated once on the untouched test set.
11. **Business insights & recommendations** — risk profiles, operational recommendations, and a cost-benefit framework.

## Models Built

| Model | Tuning | Role |
|---|---|---|
| Logistic Regression | — | Interpretable baseline (coefficients for adverse-action reasons) |
| Decision Tree | GridSearchCV | Non-linear baseline |
| Random Forest (Tuned) | Cross-validated tuning | Strong challenger |
| **XGBoost (Tuned)** | Cross-validated tuning | **Final selected model** |

## Key Results

- **Tuned XGBoost** selected using validation evidence and a pre-defined operating rule.
- At the locked **0.239 threshold**, the untouched test set produced **ROC-AUC 0.954**, **Average Precision 0.878**, **recall 0.824**, **precision 0.751**, **F1 0.786**, and **accuracy 0.910**.
- The confusion matrix was **TN 889, FP 65, FN 42, TP 196** on 1,192 test observations.
- **SMOTE** was used only within training pipelines to prevent information leakage.
- **SHAP** supports interpretation but does not by itself establish regulatory compliance; deployment would also require validated reason codes, fairness testing, monitoring and legal review.
- Strongest default drivers include prior delinquencies/derogatory reports, debt-to-income ratio
  (and whether it is disclosed), and length of credit history.

## Repository Contents

| File | Description |
|---|---|
| `Capstone_Project_Loan_Default_Prediction_Full_Code_Final_submission.ipynb` | Full-code solution notebook — the complete end-to-end analysis and modelling pipeline |
| `Capstone_Project_Loan_Default_Prediction_Full_Code_Final_submission.html` | Rendered HTML export of the notebook (all code, outputs and plots) — the graded submission format |
| `Loan_Default_Prediction_Problem_Statement.pdf` | Official problem statement / project brief |
| `hmeq.csv` | HMEQ home-equity dataset (5,960 loan applications) |

## How to Reproduce

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn imbalanced-learn xgboost shap
jupyter notebook Capstone_Project_Loan_Default_Prediction_Full_Code_Final_submission.ipynb
```

Run the cells top to bottom. Random states are fixed for reproducibility.

---

*MIT Applied AI & Data Science Program — Author: **Lycias Zembe***
