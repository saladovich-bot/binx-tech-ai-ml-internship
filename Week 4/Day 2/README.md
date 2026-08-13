# Day 2 — Cross-Validation

## Overview
Today I learned how k-fold cross-validation gives a more reliable
performance estimate than a single validation split.

## What I Did
- Applied 5-fold cross-validation using `cross_val_score`
- Reported the mean and standard deviation of F1 scores across folds
- Compared the cross-validated estimate to the single-split score from Day 1
- Confirmed stratified k-fold is used automatically for classification,
  keeping class balance consistent across folds

## Key Takeaway
A high mean with a low standard deviation means the model's performance
is stable and trustworthy, not just lucky on one split.

## Tools Used
Scikit-learn (`cross_val_score`, `StratifiedKFold`) • Pandas • Jupyter Notebook