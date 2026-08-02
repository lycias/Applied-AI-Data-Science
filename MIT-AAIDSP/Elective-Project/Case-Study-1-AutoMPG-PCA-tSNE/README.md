# Case Study 1 — Auto MPG: Dimensionality Reduction with PCA & t-SNE

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> Applying **Principal Component Analysis (PCA)** and **t-SNE** to the classic Auto MPG dataset to uncover the latent structure of vintage vehicles and derive actionable customer segments for **SecondLife**, a used-car marketplace.

## Objective

SecondLife wants to understand the natural groupings within its inventory of vintage cars so it can tailor marketing, pricing and inventory decisions. This study compresses the correlated engine/performance attributes into a small set of interpretable dimensions (PCA), visualises the non-linear structure (t-SNE), and identifies distinct vehicle segments (K-Means) to support data-driven business strategy.

## Dataset

| Property | Value |
|---|---|
| Records | 398 vehicles |
| Features | 7 (mpg, cylinders, displacement, horsepower, weight, acceleration, model year) |
| Period | 1970–1982 |
| Target of analysis | Unsupervised — no label; structure discovery |

## Techniques

- **Exploratory Data Analysis** — summary statistics, univariate distributions, count plots, correlation heatmap
- **Outlier Detection** — 1.5×IQR rule (outliers found only in horsepower, acceleration, mpg)
- **Preprocessing** — missing-value handling (horsepower `?` → median), `StandardScaler`
- **Dimensionality Reduction** — PCA (linear) and t-SNE (non-linear)
- **Clustering** — K-Means on the reduced space, with cluster profiling

## Key Findings

- **Effective compression:** just **3 principal components capture 94.26%** of the total variance (PC1 71.48%, PC2 12.37%, PC3 10.41%).
- **Interpretable axes:** PC1 is a single **"engine power vs. fuel economy"** axis (71.48%); PC2 is essentially **model year**; PC3 is essentially **acceleration**.
- **Three natural segments** (t-SNE + K-Means):

| Segment | Cars | Share | Mean MPG | Profile |
|---|---|---|---|---|
| Economy | 213 | 53.5% | 29.1 | 4-cylinder, lightweight, efficient imports |
| Mid-Range | 83 | 20.9% | 19.7 | 6-cylinder balanced American cars |
| Performance / Large | 102 | 25.6% | 14.9 | 8-cylinder muscle cars & large sedans |

## Libraries Used

`numpy` · `pandas` · `matplotlib` · `seaborn` · `scikit-learn` (`StandardScaler`, `PCA`, `TSNE`, `KMeans`)

## Files

| File | Description |
|---|---|
| `Notebook_AutoMPG_PCA_tSNE_Final.ipynb` | Executable notebook with all code, outputs and observations |
| `Notebook_AutoMPG_PCA_tSNE_Final.html` | Rendered HTML with embedded plots (submission copy) |

## Reproducibility

All stochastic steps use `random_state = 42`.

---
*MIT Applied AI & Data Science Program — Elective Project, Part 1 — Author: Lycias Zembe*
