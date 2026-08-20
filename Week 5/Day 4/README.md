# Day 4 — t-SNE & Anomaly Detection

## Overview
Using t-SNE to visualize clustering structure, comparing it to PCA, and detecting anomalies with Isolation Forest.

## Datasets
- Mall Customers dataset (Age, Annual Income, Spending Score, MinMaxScaler) — for t-SNE and anomaly detection.
- Breast Cancer Wisconsin dataset (StandardScaler) — for a direct t-SNE vs PCA comparison.

## Steps
1. Applied t-SNE to the Mall Customers data and colored the plot by the hierarchical clusters (Ward, k=5) found on Day 2.
2. Ran both PCA and t-SNE on the same Breast Cancer dataset to fairly compare the two methods.
3. Ran Isolation Forest on the Mall Customers data and reported how many points were flagged as anomalies.
4. Inspected the flagged anomalies and looked for patterns in their age, income, and spending values.

## Tools Used
Scikit-learn (TSNE, IsolationForest), Matplotlib, Jupyter Notebook

## Result
t-SNE revealed 5 clearly separated customer clusters, matching the hierarchical clustering results from Day 2. Compared on the same data, t-SNE gave a cleaner separation between classes than PCA. Isolation Forest flagged 10 customers (5%) as anomalies — mostly very high-income customers and older customers with unusually low spending.