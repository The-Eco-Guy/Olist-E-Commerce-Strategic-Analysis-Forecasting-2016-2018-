# Olist E-Commerce: Strategic Analysis & Forecasting (2016–2018)

## 📌 Project Overview

This project presents a comprehensive **data science analysis** of the **Olist E-Commerce Dataset**, covering **96,490+ unique customer orders** across Brazil.  
It follows the **complete data science lifecycle**—from data cleaning and integration to **descriptive, inferential, predictive, and prescriptive analytics**.

The primary objective is to **identify sales patterns**, **segment customer behavior**, and **derive actionable business strategies** for a large-scale online marketplace.

---

## 🚀 Key Features

### 1. Advanced Data Preparation

- **Relational Integration**  
  Merged **9 separate CSV files** into:
  - `df_master`: Fully merged dataset for recommendation systems
  - `order_level_df`: Aggregated dataset for statistical analysis

- **Dimensionality Reduction**  
  Applied **Principal Component Analysis (PCA)** to compress product dimensions  
  (`weight`, `length`, `height`, `width`) into a single feature:
  - `product_size_pca`
  - Explained **59.16% of total variance**

- **Normalization**  
  Used **Min-Max Scaling** to ensure feature parity for distance-based clustering algorithms

---

### 2. Customer Segmentation (Unsupervised Learning)

- **Model**: K-Means Clustering  
- **Validation**:
  - Elbow Method
  - Silhouette Scores: `k=2: 0.8688`, `k=3: 0.8583`, `k=4: 0.7576`, `k=5: 0.6629`
- **Optimal Clusters**: `k = 3`

#### Identified Customer Segments

| Cluster | Description | Proportion |
|-------|------------|------------|
| 0 | One-time low spenders | ~85% |
| 1 | High-spend occasional buyers | ~10% |
| 2 | Repeat low-spend buyers | ~5% |

---

### 3. Hypothesis Testing (Inferential Statistics)

All tests conducted at a **significance level (α) = 0.05**

- **One-Sample T-Test (Review Score vs 4.0)**  
  `t = 25.1946`, `p < 0.001`  
  Mean review score: `4.11`

- **Two-Sample T-Test (SP vs RJ AOV)**  
  `t = -9.7783`, `p < 0.001`  
  Means: `SP = 143.32`, `RJ = 166.85`

- **Chi-Square Test**  
  `χ² = 106.2976`, `p = 1.2136e-20`  
  Strong association between **customer segments** and **payment behavior**

- **One-Way ANOVA (Top 3 Categories)**  
  `F = 65.4335`, `p = 4.5192e-29`  
  Review scores differ significantly across top categories

---

### 4. Time-Series Forecasting (Predictive Analytics)

- **Model**: SARIMAX `(1,1,1)(1,1,1,13)`
- **Methodology**:
  - Weekly sales decomposition into **trend** and **seasonality**
  - Seasonal period: `m = 13` (quarterly patterns)
- **Outcome**:
  - Generated **13-week sales forecast**
  - Validation **RMSE: R$146,110.47**
  - Useful for **inventory planning** and **budget allocation**

---

### 5. Recommender System (Prescriptive Analytics)

- **Algorithm**: Apriori (Association Rule Mining)
- **Objective**: Identify frequent itemsets for:
  - Cross-selling
  - Bundling strategies

#### Key Insights

| Product Pair | Lift |
|-------------|------|
| Watches & Gifts → Audio | **18.15** |
| Bed & Bath → Home Comfort | **3.15** |

---

## 🛠️ Tech Stack

- **Language**: Python  
- **Data Handling**: Pandas, NumPy  
- **Visualization**: Matplotlib, Seaborn  
- **Machine Learning**:  
  - Scikit-Learn (KMeans, PCA, MinMaxScaler)
- **Statistics & Time Series**:  
  - SciPy  
  - Statsmodels (ADF Test, SARIMAX)
- **Association Rules**:  
  - Mlxtend (Apriori Algorithm)

---

## 📈 Outcomes & Business Impact

- Data-driven **customer segmentation** for targeted marketing
- Statistically validated **regional and category-level insights**
- Actionable **sales forecasts** for operational planning
- High-lift **product bundling strategies** to improve revenue
