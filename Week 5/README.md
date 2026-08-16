# Week 5 — Unsupervised Learning

BinX Tech AI/ML Internship — Phase 2 → 3 transition (40 hours, 5 training days)

## Overview
Week 5 covers unsupervised learning: clustering, dimensionality reduction, and anomaly detection — all on data with no labels. The week closes with selecting a Phase 3 capstone project and planning Sprint 1.

## Daily Breakdown

| Day | Topic | Key Deliverable |
|---|---|---|
| Day 1 | K-Means Clustering | Elbow method + silhouette analysis, final clusters, interpretation |
| Day 2 | DBSCAN & Hierarchical Clustering | Method comparison notebook (K-Means vs DBSCAN vs hierarchical) |
| Day 3 | PCA | Cumulative explained-variance plot, justified component count |
| Day 4 | t-SNE & Anomaly Detection | 2D visualization + Isolation Forest results |
| Day 5 | Phase 3 Project Selection & Sprint 1 Planning | Signed-off project scope, problem statement, Sprint 1 backlog |

## Day 1 Summary — K-Means Clustering
- **Dataset:** Mall Customer Segmentation Data (Age, Annual Income, Spending Score)
- **Scaling:** MinMaxScaler applied before clustering
- **Chosen k:** 3 (confirmed by both elbow method and silhouette score: 0.688 vs 0.584 for k=4)
- **Result:** Customers split into 3 groups — young big spenders, moderate mixed-age spenders, and consistently low spenders across ages.

*(Days 2–5 to be added as completed.)*

## Tools Used
Scikit-learn (KMeans, DBSCAN, PCA, TSNE, IsolationForest) • SciPy (hierarchical/dendrogram) • Matplotlib • Pandas • Jupyter Notebook • Git & GitHub