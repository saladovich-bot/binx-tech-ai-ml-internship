# Day 5 — Scikit-learn Pipelines & Tuned Mini-Project

## Overview
This is the Week 4 capstone: a single leak-free Pipeline that chains
preprocessing and modeling together, tuned end-to-end with GridSearchCV,
and evaluated once on a held-out test set.

## Dataset
**IBM HR Analytics Employee Attrition & Performance** (1,470 employees,
35 features). Binary classification task: predict whether an employee
will leave the company (`Attrition`: Yes/No). The dataset is imbalanced
(~84% stayed, ~16% left), which required careful, honest evaluation
throughout.

## Workflow

### 1. Exploratory Data Analysis
- Checked class balance, distributions of key numeric features
  (Age, MonthlyIncome), and correlations between numeric features
- Compared attrition across JobRole, JobSatisfaction, and WorkLifeBalance
- Found that OverTime, JobRole, and low satisfaction scores are strongly
  associated with higher attrition

### 2. Feature Engineering
Created two new features:
- `IncomePerYearWorked` — monthly income relative to years of experience,
  capturing whether an employee may be underpaid relative to their
  background
- `PromotionGapRatio` — share of an employee's tenure spent without a
  promotion, as a proxy for career stagnation

### 3. Pipeline & ColumnTransformer
Built a single `Pipeline` combining:
- `ColumnTransformer` with `StandardScaler` for numeric columns and
  `OneHotEncoder` for categorical columns
- `LogisticRegression` with `class_weight="balanced"` to handle the
  class imbalance

This design makes data leakage structurally impossible: scaling and
encoding are fit only on the training portion of each cross-validation
fold.

### 4. Hyperparameter Tuning
Tuned the pipeline's `C` parameter with `GridSearchCV` (5-fold CV,
scoring="f1"). Best parameter: `C = 0.1`.

### 5. Results

| Metric | Baseline (single split) | Cross-Validated | Tuned (GridSearchCV) |
|---|---|---|---|
| F1 (class "Yes") | 0.45 | 0.507 (± 0.066) | 0.507 |
| Test set F1 | — | — | reported below |
| ROC AUC | — | — | 0.82 |

On the held-out test set, the final model correctly identified 32 out
of 47 employees who actually left the company (recall ≈ 68%), with an
ROC AUC of 0.82 — showing the model separates the two classes well
overall, even though F1 alone (sensitive to threshold and small
positive-class size) looks more modest.

### 6. Evaluation Visuals
- Confusion matrix: shows correct/incorrect predictions per class
- ROC curve (AUC = 0.82): shows overall class separation
- Feature coefficients: shows which features influenced the model most

## Key Takeaway
A single F1 score can be misleading on an imbalanced dataset with a
small positive class. Looking at F1 alongside recall, the confusion
matrix, and ROC AUC gives a more honest picture of model performance.
Wrapping everything in a Pipeline + ColumnTransformer made the whole
workflow leak-free and reproducible — the same structure required for
the Phase 3 capstone.

## Tools Used
Scikit-learn (Pipeline, ColumnTransformer, GridSearchCV, LogisticRegression)
- Pandas • Matplotlib • Seaborn • Jupyter Notebook • Git & GitHub