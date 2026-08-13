# Week 4 — Evaluation, Tuning & Pipelines

BinX Tech AI & ML Internship Program — Phase 2, Week 4 (40 hours, 5 training days)

## Overview
This week focused on turning a model that runs into a model that can be
trusted. I learned to evaluate models reliably with cross-validation,
diagnose overfitting and underfitting, engineer better features, tune
hyperparameters with GridSearchCV, and package the full workflow into a
clean, leak-free Scikit-learn Pipeline.

## Daily Breakdown

| Day | Topic | Notebook |
|---|---|---|
| Day 1 | Train / Validation / Test Splits | [day1](./day1) |
| Day 2 | Cross-Validation (k-fold, stratified k-fold) | [day2](./day2) |
| Day 3 | Bias-Variance Trade-off & Diagnosing Model Fit | [day3](./day3) |
| Day 4 | Feature Engineering & Hyperparameter Tuning | [day4](./day4) |
| Day 5 | Scikit-learn Pipelines & Tuned Mini-Project | [day5](./day5) |

*(update the links above to match your actual folder/file names)*

## Week 4 Deliverables
- Three-way split notebook demonstrating correct train/validation/test discipline
- Cross-validation notebook reporting mean and standard deviation across folds
- Bias-variance notebook with diagnosed overfit/underfit cases and fixes
- Feature-engineering and GridSearchCV notebook with engineered features
  and best hyperparameters
- Week 4 tuned pipeline mini-project: a leak-free Pipeline + ColumnTransformer,
  tuned and evaluated on held-out data (Day 5)

## Day 5 Highlight
The week closes with a single tuned pipeline built on the **IBM HR
Employee Attrition dataset** (1,470 employees), predicting employee
attrition with Logistic Regression inside a leak-free Pipeline +
ColumnTransformer, tuned via GridSearchCV. Final results: F1 ≈ 0.51
(cross-validated), ROC AUC = 0.82. See [day5/README.md](./day5/README.md)
for full details.

## Key Concepts Learned
- Why a single test set gives misleading results when tuned against repeatedly
- k-fold and stratified k-fold cross-validation
- The bias-variance trade-off and how to diagnose model fit
- Feature engineering techniques and why they often beat model choice
- Hyperparameter tuning with GridSearchCV
- Building leak-free Pipelines with ColumnTransformer

## Tools Used
Python 3.10+ • Pandas • Scikit-learn • Matplotlib • Seaborn • Jupyter Notebook • Git & GitHub