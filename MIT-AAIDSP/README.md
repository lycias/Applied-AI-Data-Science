# MIT Applied AI & Data Science Program (AAIDSP)

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![Status](https://img.shields.io/badge/Elective-Complete-brightgreen)
![Status](https://img.shields.io/badge/Capstone-Complete-brightgreen)

> Portfolio of coursework completed as part of the **MIT Applied AI & Data Science Program** — a hands-on program covering the end-to-end data science workflow, from exploratory data analysis and preprocessing to machine learning, unsupervised learning, and applied business problem solving.

This directory collects the graded deliverables for the program. It contains the completed **Elective Project** (two unsupervised-learning case studies) and the completed **Capstone Project** (a supervised-learning loan-default prediction problem).

## Contents

| Module | Description | Status |
|---|---|---|
| [Elective Project](./Elective-Project) | Two unsupervised-learning case studies applying PCA, t-SNE and clustering to real-world datasets | ✅ Complete |
| [Capstone Project](./Capstone-Project) | Loan Default Prediction — supervised binary classification on the HMEQ dataset (Logistic Regression, Decision Tree, Random Forest; SMOTE; SHAP) | ✅ Complete |

## Elective Project — Case Studies

| # | Case Study | Techniques | Status |
|---|---|---|---|
| 1 | [Auto MPG — PCA & t-SNE](./Elective-Project/Case-Study-1-AutoMPG-PCA-tSNE) | EDA, IQR outlier detection, StandardScaler, PCA, t-SNE, K-Means | ✅ Complete |
| 2 | [AllLife Bank — Customer Segmentation](./Elective-Project/Case-Study-2-AllLife-Bank-Segmentation) | EDA, IQR Winsorization, Log Transform, VIF, PCA, K-Means, GMM, K-Medoids | ✅ Complete |

## Capstone Project — Loan Default Prediction

| Aspect | Detail |
|---|---|
| **Problem** | Binary classification — predict loan default (`BAD`) on the HMEQ home-equity dataset (5,960 applications) |
| **Techniques** | EDA, missingness flags, IQR winsorization, feature engineering, SMOTE, threshold tuning |
| **Models** | Logistic Regression, Decision Tree (GridSearchCV), Random Forest (RandomizedSearchCV) |
| **Explainability** | Random Forest & permutation importance, SHAP values |
| **Outcome** | Tuned Random Forest selected; threshold optimised for recall on defaulters |
| **Details** | [Capstone-Project »](./Capstone-Project) |

## Reproducibility

All stochastic steps use a fixed random seed (`42`) to ensure fully reproducible results.

---
*MIT Applied AI & Data Science Program — Author: Lycias Zembe*
