# Loan Default Prediction — MIT AAIDSP Capstone Project

![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
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
- **Modelling:** scikit-learn (Logistic Regression, Decision Tree, Random Forest, GridSearchCV, RandomizedSearchCV)
- **Class imbalance:** imbalanced-learn (**SMOTE**)
- **Explainability:** **SHAP**, permutation importance

## Approach & Workflow

1. **Data inspection** — load HMEQ (5,960 rows, 12 predictors + `BAD` target); assess types and missingness.
2. **Exploratory Data Analysis** — univariate, target, bivariate and multivariate analysis.
3. **Preprocessing** — median/mode imputation with a **missingness flag** (`DEBTINC` is ~21% missing and its absence is itself predictive), IQR winsorization of outliers, feature engineering, and categorical encoding.
4. **Train/test split & scaling** — stratified split preserving the ~20% default rate.
5. **Class imbalance** — **SMOTE** applied on the training set to balance the ~80:20 class ratio.
6. **Model building** — Logistic Regression, Decision Tree, and Random Forest.
7. **Hyperparameter tuning** — Decision Tree via **GridSearchCV**, Random Forest via **RandomizedSearchCV**.
8. **Model comparison & selection** — models compared on ROC-AUC, recall, F1 and accuracy.
9. **Feature importance & explainability** — Random Forest importances, permutation importance, and **SHAP** values.
10. **Threshold optimisation** — decision cutoff lowered below 0.5 to maximise recall on defaulters.
11. **Business insights & recommendations** — risk profiles, operational recommendations, and a cost-benefit framework.

## Models Built

| Model | Tuning | Role |
|---|---|---|
| Logistic Regression | — | Interpretable baseline (coefficients for adverse-action reasons) |
| Decision Tree | GridSearchCV | Non-linear baseline |
| **Random Forest (Tuned)** | RandomizedSearchCV | **Final selected model** |

## Key Results

- **Tuned Random Forest** selected as the final model — best ROC-AUC and recall while generalising
  well under cross-validation.
- **SMOTE** used to handle the class imbalance (~80:20 repay:default ratio).
- **Decision threshold tuned** (below 0.5) to optimise **recall for the default class**, aligning
  the model with the bank's asymmetric cost structure.
- **SHAP** and Logistic Regression coefficients provide per-decision explanations, supporting
  regulatory compliance (e.g. adverse-action reasons under the Equal Credit Opportunity Act).
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
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn shap
jupyter notebook Capstone_Project_Loan_Default_Prediction_Full_Code_Final_submission.ipynb
```

Run the cells top to bottom. Random states are fixed for reproducibility.

---

*MIT Applied AI & Data Science Program — Author: **Lycias Zembe***
