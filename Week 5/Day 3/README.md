# Day 3 — Dimensionality Reduction with PCA

## Overview
Using PCA to reduce a high-dimensional dataset (30 features) down to fewer dimensions, while keeping most of the important information.

## Dataset
Breast Cancer Wisconsin dataset (sklearn) — 30 numeric features, scaled with StandardScaler.

## Steps
1. Scaled the dataset with StandardScaler.
2. Fit PCA on all components and plotted cumulative explained variance against the number of components.
3. Found that 10 components retain about 95% of the total variance.
4. Reduced the data to 2 components and plotted a 2D scatter plot, colored by diagnosis (malignant/benign).
5. Documented what the reduction preserved and what it cost.

## Tools Used
Scikit-learn (PCA), StandardScaler, Matplotlib, Jupyter Notebook

## Result
10 out of 30 components keep ~95% of the data's variance. Even reducing all the way down to just 2 components (~63% variance) still shows a clear visual separation between malignant and benign tumors, mostly along Principal Component 1.