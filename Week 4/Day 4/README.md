# Day 4 — Feature Engineering & Hyperparameter Tuning

## Overview
Today I learned how engineering better features often improves results
more than choosing a fancier model, and how to tune hyperparameters
systematically with GridSearchCV.

## What I Did
- Created at least two new engineered features and justified each
- Defined a hyperparameter grid for a model from Week 3
- Ran GridSearchCV with 5-fold cross-validation
- Compared the tuned model's cross-validated score against the untuned
  baseline

## Key Takeaway
Hyperparameters (set before training) are different from parameters
(learned during training). GridSearchCV searches combinations
systematically and cross-validates each one, avoiding lucky single splits.

## Tools Used
Scikit-learn (`GridSearchCV`) • Pandas • Jupyter Notebook