
# Hospital Revenue Prediction

## Overview
This project clusters insurance companies based on their annual claim payments to a hospital from 2018 to 2022. The primary objective is to analyze payment behavior patterns using time-series clustering with Dynamic Time Warping (DTW).

## Data Description
- Data Source: Revenue reports per payer for years 2018 to 2022.
- Each file includes columns:
  - `Payer`: Name of the insurance company.
  - `Emergency`, `Health Checkup`, `Inpatient`, `Outpatient`: Claim payment values for each service type.

## Methodology
### 1. Data Preprocessing
- Merged five yearly datasets.
- Identified 735 unique payers across all years.
- Generated time-series data for each payer with 5 data points (2018–2022) for each category.
- Focused on the `Total` payment across all services as the feature for clustering.

### 2. Clustering Approach
- **Distance Metric**: Dynamic Time Warping (DTW)
- **Clustering Algorithm**: TimeSeriesKMeans (from `tslearn`)
- **Normalization**: MinMaxScaler applied to each payer's time series.

### 3. Cluster Optimization
- Initial number of clusters set as `ceil(sqrt(N)) = 28`.
- Visualizations were plotted for each cluster.
- Silhouette Score analysis was used to find optimal cluster number.
- **Optimal Number of Clusters**: 3

## Results
### Cluster Interpretations:
- **Cluster 0**: Payers with low revenues from 2018–2021 and a sharp increase in 2022.
- **Cluster 1**: Payers with increasing trends from 2018–2021 followed by a significant drop in 2022.
- **Cluster 2**: Payers with high payments in 2018, sharp decline in 2019, and remained low.

## Visualization
- Cluster trends plotted using Plotly.
- Average trend line (in red) shown for each cluster.
- Bar chart representing the number of payers per cluster.

## Key Insights
- Time-series clustering reveals structural payment behavior changes.
- Can assist hospital management to:
  - Identify consistent payers.
  - Detect risk of declining revenue from specific payers.
  - Formulate engagement strategies for different payer profiles.

## Libraries Used
- `tslearn`, `scikit-learn`, `numpy`, `pandas`, `matplotlib`, `plotly`

## Next Steps
- Apply clustering per service type (e.g., inpatient only).
- Introduce forecasting models (e.g., LSTM) per cluster.
- Enrich analysis with external factors like economic indicators or policy changes.


