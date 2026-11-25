# Socioeconomic Country Clustering (DS203 Project)

Unsupervised exploratory analysis, dimensionality reduction, and clustering of **217 countries** using **2022 World Development Indicators (WDI)** data (`WDICSV.csv`).

## Overview & Pipeline

1. **Data Preparation & Filtering**
   - Extracts 11 socioeconomic indicators for 2022 and merges regional and World Bank income group metadata.
   - Filters to entities with assigned `Region` and `Income Group` labels (217 countries).

2. **Exploratory Data Analysis (EDA) & Skewness Handling**
   - Summarizes missingness, summary statistics, skewness, and extreme values.
   - Applies a natural log transformation to right-skewed `GDP Per Capita` (`log_gdp_per_capita`).

3. **Preprocessing & Correlation Analysis**
   - Imputes missing numerical values (median imputation) and standardizes features (mean = 0, standard deviation = 1) prior to dimensionality reduction and distance-based clustering.
   - Computes and visualizes pairwise indicator correlations.

4. **Principal Component Analysis (PCA)**
   - Evaluates eigenvalues, individual/cumulative explained variance ratios, and component loadings across all 11 features.
   - Projects countries into a 2D PCA space (`PC1` and `PC2`, capturing ~50.2% of total variance) for visualization and clustering.

5. **K-Means Clustering, Profiling & Outlier Detection**
   - Tunes cluster count K using inertia (elbow method) and silhouette scores. (K = 5)
   - Fits K-Means on the PCA representation, profiles cluster indicator means, cross-tabulates clusters against `Income Group` and `Region`, and ranks unusual countries by Euclidean distance to their assigned cluster centroid.

## Repository Contents

- `ds203_Proj_final_merged.ipynb`: The completed implementation.
- `README.md`: Project documentation.
