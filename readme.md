# 🏥 Hospital Revenue Prediction  
**Time-Series Clustering of Insurance Claim Payments Using DTW & KMeans**

## 📌 Project Overview

This project aims to perform a clustering analysis on the **claim payment trends of insurance companies** to a hospital from **2018 to 2022**. By using **time-series clustering** with **Dynamic Time Warping (DTW)** as the distance metric and **K-Means**, we can identify patterns in insurer payment behavior and segment them into meaningful groups.

---

## 📊 Dataset Description

- **Files**:  
  - `Revenue Per Payer 2018.xlsx`  
  - `Revenue Per Payer 2019.xlsx`  
  - `Revenue Per Payer 2020.xlsx`  
  - `Revenue Per Payer 2021.xlsx`  
  - `Revenue Per Payer 2022.xlsx`

- **Columns**:
  - `Payer` (Insurance company name)
  - `Emergency`, `Health Checkup`, `Inpatient`, `Outpatient` (Claim amounts per service type)

- **Unique Entities**: 735 unique insurance companies over 5 years

---

## 🧠 Methodology

### ⏳ Time-Series Preparation

- Each payer’s data is transformed into a time-series of total yearly payments (2018–2022).
- Zero is used for years where a payer didn’t make any claims.

### 📈 Scaling

- All time-series are Min-Max scaled to normalize variations and prepare for clustering.

### 🔍 Clustering Approach

- **Algorithm**: TimeSeriesKMeans from `tslearn`  
- **Distance Metric**: `dtw` (Dynamic Time Warping)  
- **Cluster Count Selection**:
  - Initial exploration: √n ≈ 28 clusters
  - Optimal cluster (Silhouette Score): **3 clusters**

---

## 🧩 Cluster Insights

### ✅ Final Clusters (K=3)

| Cluster | Pattern Description                                                             |
|---------|----------------------------------------------------------------------------------|
| 0       | 🚀 Low payments 2018–2021, sharp increase in 2022                               |
| 1       | 📉 Gradual rise from 2018–2021, but drop significantly in 2022                  |
| 2       | 📉 High payments in 2018, followed by major decline with no recovery until 2022 |

### 📊 Cluster Distribution (out of 735 total payers)

| Cluster | Number of Members |
|---------|-------------------|
| 0       | ~224              |
| 1       | ~189              |
| 2       | ~322              |

---

## 📈 Evaluation

- **Silhouette Score Analysis** performed from K=2 to K=30
- **Best K**: 3 (based on highest silhouette score)

---

## 💡 Business Insights

- Cluster 0 can represent **new strategic partners** with increasing potential.
- Cluster 1 may represent **at-risk relationships** needing retention strategies.
- Cluster 2 includes **legacy partners** whose engagement dropped – potential for reactivation.

---

## 📦 Tech Stack

- Python  
- Libraries: `tslearn`, `scikit-learn`, `pandas`, `plotly`, `matplotlib`

---

## ✍️ Author

**Alexander Tiopan**  
_Data Analyst | Healthcare Data Research | Time Series Enthusiast_  
📧 alexandertiopan1212@gmail.com  
📂 Repository: [Hospital_Revenue_Prediction](https://github.com/alexandertiopan1212/Hospital_Revenue_Prediction)
