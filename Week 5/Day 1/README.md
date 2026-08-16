# Day 1 — K-Means Clustering

## Overview
This notebook covers the first hands-on lab of Week 5 (Unsupervised Learning). The goal is to cluster mall customers into groups based on their age, income, and spending behavior, without using any labels — the model discovers the structure on its own.

## Dataset
**Mall Customer Segmentation Data** (Kaggle)
Features used: `Age`, `Annual Income (k$)`, `Spending Score (1-100)`

## Steps

1. **Scaling** — Applied `MinMaxScaler` to `Age`, `Annual Income (k$)`, and `Spending Score (1-100)` so all features are on the same 0–1 scale before clustering.

2. **Elbow Method** — Ran K-Means for k = 1 to 10 and plotted inertia against k. The curve bends sharply around **k=3**, after which inertia decreases only slightly.

3. **Silhouette Score** — Compared k=3 and k=4:
   - k=3 → 0.688
   - k=4 → 0.584

   k=3 scored higher, confirming the elbow method result.

4. **Final Model & Visualization** — Fit K-Means with **k=3** and plotted the clusters (Age vs Spending Score) in a 2D scatter plot, colored by cluster label.

5. **Interpretation**

| Cluster | Description |
|---|---|
| Cluster 0 (Green) | Young customers with a high spending score — big spenders despite their age. |
| Cluster 1 (Blue) | Mixed-age customers with a moderate spending score — average spenders. |
| Cluster 2 (Red) | Customers across most ages, but all with a low spending score — low spenders. |

**Takeaway:** Age alone doesn't fully explain spending behavior — the clusters mainly separate customers by *how much* they spend, not just *how old* they are.

## Tools Used
Scikit-learn (`KMeans`, `MinMaxScaler`, `silhouette_score`) • Matplotlib • Pandas • Jupyter Notebook

## Files
- `day1_kmeans_clustering.ipynb` — full notebook with elbow method, silhouette analysis, final model, and interpretation