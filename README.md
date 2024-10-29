# CryptoClustering

## Overview

CryptoClustering is a data analysis project that applies K-Means clustering and Principal Component Analysis (PCA) to classify cryptocurrencies based on their price fluctuations over various timeframes. The project examines price changes over intervals spanning 24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year.

## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Data](#data)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Analysis Steps](#analysis-steps)
  - [Prepare the Data](#prepare-the-data)
  - [Find the Best Value for K Using the Original Scaled DataFrame](#find-the-best-value-for-k-using-the-original-scaled-dataframe)
  - [Cluster Cryptocurrencies with K-Means Using the Original Scaled Data](#cluster-cryptocurrencies-with-k-means-using-the-original-scaled-data)
  - [Optimize Clusters with Principal Component Analysis](#optimize-clusters-with-principal-component-analysis)
  - [Find the Best Value for K Using the PCA Data](#find-the-best-value-for-k-using-the-pca-data)
  - [Cluster the Cryptocurrencies with K-Means Using the PCA Data](#cluster-the-cryptocurrencies-with-k-means-using-the-pca-data)
  - [Determine the Weights of Each Feature on Each Principal Component](#determine-the-weights-of-each-feature-on-each-principal-component)
- [Results](#results)

## Project Structure


- **Resources/**: Contains the dataset used in the analysis.
- **Crypto_Clustering.ipynb**: Jupyter Notebook containing the code and analysis.

## Data

The dataset `crypto_market_data.csv` includes the following columns:

- `coin_id`: The unique identifier for each cryptocurrency.
- `price_change_percentage_24h`: Price change percentage over the last 24 hours.
- `price_change_percentage_7d`: Price change percentage over the last 7 days.
- `price_change_percentage_30d`: Price change percentage over the last 30 days.
- `price_change_percentage_60d`: Price change percentage over the last 60 days.
- `price_change_percentage_200d`: Price change percentage over the last 200 days.
- `price_change_percentage_1y`: Price change percentage over the last year.

## Prerequisites

- Python 3.7 or higher
- Anaconda or virtualenv for environment management
- Jupyter Notebook

## Installation

1. **Clone the Repository**
    git clone https://github.com/ilikeitrhough/CryptoClustering.git
   cd CryptoClustering

2. **Create a Virtual Environment**
    Copy code
    conda create -n cryptocluster python=3.8
    conda activate cryptocluster

3. **Install Required Packages**
    Copy code
    pip install pandas scikit-learn matplotlib


## Analysis Steps
* Prepare the Data
* Find the Best Value for K Using the Original Scaled DataFrame
* Cluster Cryptocurrencies with K-Means Using the Original Scaled Data
* Optimize Clusters with Principal Component Analysis
* Find the Best Value for K Using the PCA Data
* Cluster the Cryptocurrencies with K-Means Using the PCA Data
* Determine the Weights of Each Feature on Each Principal Component

## Results
#### Optimal Number of Clusters (k): 
The elbow method suggested that the best value for k is 4 for both the original scaled data and the PCA data.

#### Explained Variance by PCA: 
The three principal components explain approximately 89.49% of the variance in the dataset.

#### Cluster Visualization:
* Original Data: Clusters are visualized using 24h and 7d price changes.
* PCA Data: Clusters are visualized using the first two principal components.

#### Feature Influence on Principal Components:
**PCA1** Strongest: price_change_percentage_200d | Weakest: price_change_percentage_24h\
**PCA2** Strongest: price_change_percentage_30d  | Weakest: price_change_percentage_1y\
**PCA3** Strongest: price_change_percentage_7d   | Weakest: price_change_percentage_60d 

Conclusion
The CryptoClustering project successfully classified cryptocurrencies into distinct clusters based on their price change percentages over various timeframes. The dimensionality of the data was reduced while retaining most of the variance. The consistent optimal k value before and after PCA indicates that the underlying cluster structure is robust.