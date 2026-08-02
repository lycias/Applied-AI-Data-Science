# Case Study 2 — AllLife Bank: Credit Card Customer Segmentation

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> Segmenting **AllLife Bank's** credit-card customers with unsupervised learning to enable personalised marketing and improved service delivery — validated across **three independent clustering algorithms**.

## Objective

AllLife Bank wants to identify natural segments among its credit-card customers based on their behavioural profile (spending, credit limit, and channel-usage patterns). Robust, well-separated segments allow the bank to personalise product offers, optimise service channels, and prioritise high-value relationships. This study derives those segments and cross-validates them using K-Means, Gaussian Mixture Models, and K-Medoids (PAM).

## Dataset

| Property | Value |
|---|---|
| Records | 660 customers (655 after removing duplicates) |
| Features | 5 behavioural attributes |
| Target of analysis | Unsupervised — customer segmentation |

## Techniques

- **Exploratory Data Analysis** — summary statistics, distributions, outlier inspection, correlation heatmap, pairplot
- **Preprocessing** — duplicate removal, **IQR Winsorization** of extreme values, **log transformation** of skewed features
- **Multicollinearity check** — **Variance Inflation Factor (VIF)**
- **Dimensionality Reduction** — PCA
- **Clustering** — **K-Means**, **Gaussian Mixture Model (GMM)**, **K-Medoids (PAM)** — with elbow & silhouette-based model selection
- **Validation** — cross-algorithm agreement via Adjusted Rand Index (ARI)

## Key Findings

- **Effective compression:** **3 principal components capture 88.06%** of the total variance.
- **Robust segmentation:** all **three algorithms converge on the same 3 segments** (ARI = 1.0), with a silhouette score of **0.5875**.

| Segment | Customers | Share | Avg. Credit Limit | Profile |
|---|---|---|---|---|
| Mid-Tier In-Branch | 381 | 58.2% | \$33,675 | Mainstream customers favouring in-branch service |
| Premium Digital | 49 | 7.5% | \$140,102 | High-limit, digitally engaged premium customers |
| Low-Tier Phone-Dependent | 225 | 34.4% | \$12,151 | Lower-limit customers reliant on phone banking |

## Libraries Used

`numpy` · `pandas` · `matplotlib` · `seaborn` · `scikit-learn` (`StandardScaler`, `PCA`, `KMeans`, `GaussianMixture`) · `statsmodels` (VIF) · K-Medoids (PAM)

## Files

| File | Description |
|---|---|
| `Notebook_AllLife_Bank_Final.ipynb` | Executable notebook with all code, outputs and observations |
| `Notebook_AllLife_Bank_Final.html` | Rendered HTML with embedded plots (submission copy) |

## Reproducibility

All stochastic steps use `random_state = 42`.

---
*MIT Applied AI & Data Science Program — Elective Project, Part 2 — Author: Lycias Zembe*
