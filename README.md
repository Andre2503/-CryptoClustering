# Crypto Market Data Analysis

## Overview
This repository uses unsupervised machine learning clustering techniques to understand underlying patterns in the crypto market. The project involves data preparation, scaling, clustering using K-Means, and optimization with Principal Component Analysis (PCA).

## Repository Structure
- **Started_Code**: 
  - **Resources**: Contains the `crypto_market_data.csv` file, which is the primary dataset for the analysis.
  - **Crypto_Clustering.ipynb**: The Jupyter Notebook containing the complete analysis script.

## Analysis Steps

### 1. Data Preparation
- The data from `crypto_market_data.csv` is normalized using `StandardScaler()` from scikit-learn.
- A DataFrame with the scaled data is created, retaining the "coin_id" as the index.

### 2. Identifying best k value for KMeans
- The elbow method is employed to find the optimal value of k.
- A range of k values from 1 to 11 is tested, and inertia values are calculated to identify the best k value.
- Best value identified through this method is `4`

### 3. Clustering Cryptocurrencies with K-means
- The K-means model is initialized and fitted using the optimal k value of 4.
- Clusters are predicted and a scatter plot is created using hvPlot, setting "24h Price Change (%)" and "7d Price Change (%)" as axes.

### 4. Applying Principal Component Analysis
- PCA is applied to the original scaled data, reducing features to three principal components.
- The explained variance is calculated to understand the information retained in the principal components.
- A new DataFrame with PCA data is created, maintaining "coin_id" as the index.

### 5.  Identifying best k value Using the PCA Data
- The elbow method is repeated on the PCA data to find the best k value (result was 4).
- A comparison is made between the best k values found using the original data and the PCA data.

### 6. Clustering Cryptocurrencies with K-means Using the PCA Data
- The K-means model is applied to the PCA data using `n_clusters=4`.
- Clusters are predicted, and a scatter plot is generated with "PCA1" and "PCA2" as axes.

### Conclusion
The analysis concludes with insights into the impact of using fewer features (via PCA) on the K-Means clustering.

## How to Use
To replicate this analysis:
1. Clone the repository.
2. Ensure Jupyter Notebook is installed on your system.
3. Open `Crypto_Clustering.ipynb` in Jupyter Notebook and run the cells.

## Dependencies
- Python
- Pandas
- scikit-learn
- hvPlot
- Jupyter Notebook

