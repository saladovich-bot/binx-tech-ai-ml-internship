# Day 2 — DBSCAN & Hierarchical Clustering

## Overview
Comparing three clustering methods (K-Means, DBSCAN, Hierarchical) on the Mall Customers dataset to see which one best fits the data's shape.

## Dataset
Mall Customers dataset — Age, Annual Income (k$), Spending Score (1-100), scaled with MinMaxScaler.

## Steps
1. Ran DBSCAN on the scaled data and reported the number of clusters and noise points found.
2. Built a hierarchical clustering dendrogram using Ward linkage and chose a cut height to get 5 clusters.
3. Compared K-Means, DBSCAN, and Hierarchical results on the same data.
4. Documented which method best fits this dataset's shape and why.

## Tools Used
Scikit-learn (DBSCAN), SciPy (dendrogram, linkage, fcluster), Matplotlib, Jupyter Notebook

## Result
Hierarchical clustering (Ward linkage, k=5) gave the most well-separated and interpretable customer segments compared to K-Means and DBSCAN.