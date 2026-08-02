# Elective Project — Unsupervised Learning

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![Marks](https://img.shields.io/badge/Each%20Part-30%20Marks-blue)

> The Elective Project comprises **two independent case studies** (30 marks each), each applying the full unsupervised-learning workflow — exploratory data analysis, preprocessing, dimensionality reduction and clustering — to a distinct real-world business problem.

## Case Studies

| # | Title | Dataset | Techniques | Key Findings |
|---|---|---|---|---|
| 1 | **Auto MPG — PCA & t-SNE** | 398 vintage cars, 7 features (1970–1982) | EDA · IQR outlier detection · StandardScaler · PCA · t-SNE · K-Means | 3 PCs capture **94.26%** of variance; PC1 = "engine power vs. economy" axis (71.48%); 3 segments — Economy (213 cars, 53.5%), Mid-Range (83, 20.9%), Performance (102, 25.6%) |
| 2 | **AllLife Bank — Customer Segmentation** | 660 credit-card customers, 5 behavioural features (655 post-cleaning) | EDA · IQR Winsorization · Log Transform · VIF · PCA · K-Means · GMM · K-Medoids | 3 PCs capture **88.06%** of variance; 3 segments confirmed by all algorithms (ARI = 1.0), silhouette = 0.5875 — Mid-Tier In-Branch (58.2%), Premium Digital (7.5%), Low-Tier Phone-Dependent (34.4%) |

## Folder Structure

```
Elective-Project/
├── README.md
├── Case-Study-1-AutoMPG-PCA-tSNE/
│   ├── Notebook_AutoMPG_PCA_tSNE_Final.ipynb
│   ├── Notebook_AutoMPG_PCA_tSNE_Final.html
│   └── README.md
└── Case-Study-2-AllLife-Bank-Segmentation/
    ├── Notebook_AllLife_Bank_Final.ipynb
    ├── Notebook_AllLife_Bank_Final.html
    └── README.md
```

Each case study ships with both the executable Jupyter notebook (`.ipynb`) and a rendered `.html` version with all outputs and plots embedded.

---
*MIT Applied AI & Data Science Program — Author: Lycias Zembe*
