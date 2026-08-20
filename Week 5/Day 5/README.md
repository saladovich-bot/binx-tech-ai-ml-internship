# Day 5 — Phase 3 Project Selection & Sprint 1 Planning

## Project Selected
**Cardiac Patient Monitoring System** — an individual AI/ML project built earlier in the internship, using a synthetic cardiac dataset.

## Problem Statement
Build a machine learning system that classifies patient cardiac risk based on synthetic health data (heart rate, blood pressure, age, and related features), comparing multiple models and improving performance through feature engineering.

## Definition of Done
- A clean, documented Jupyter Notebook covering the full pipeline (EDA → preprocessing → modeling → evaluation)
- At least two trained models compared using cross-validation and standard metrics (accuracy, F1, ROC-AUC)
- Feature engineering applied to improve model performance over the baseline
- A GitHub repository with a clean README, requirements.txt, and result outputs (plots, summaries)
- A short technical write-up summarizing results and limitations

## Weekly Plan & Progress

| Stage | Planned Work | Status |
|---|---|---|
| Data preparation | Load synthetic cardiac dataset, clean and explore (EDA) | ✅ Done |
| Baseline modeling | Train Logistic Regression and Random Forest, compare with cross-validation | ✅ Done |
| Feature engineering | Add `hr_bp_ratio` and `age_group`, tune with GridSearchCV | ✅ Done |
| Evaluation | Compare models using F1 and ROC-AUC, document results | ✅ Done |
| Documentation | Write README, data dictionary, and limitations section | ✅ Done |

## Results Summary
- Logistic Regression outperformed Random Forest on test accuracy, cross-validated F1, and ROC-AUC.
- Feature engineering (`hr_bp_ratio`, `age_group`) plus GridSearchCV tuning improved Logistic Regression's F1 score from 0.677 to 0.710.

## Note
This project was completed as an individual project earlier in the internship rather than as a new Phase 3 capstone, since the internship is ending ahead of schedule. It already meets the program's professional baseline (documented notebook, trained models, evaluated results, clean repository), so it is presented here as the completed Sprint 1–4 equivalent for Week 5 sign-off.