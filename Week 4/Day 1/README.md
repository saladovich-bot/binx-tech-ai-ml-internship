# Day 1 — Train / Validation / Test Splits

## Overview
Today I learned why a single train/test split is not enough for reliable
model evaluation, and how to create a proper three-way split.

## What I Did
- Learned why tuning against the test set produces misleading results
- Created a three-way split (train / validation / test) using
  `train_test_split` twice
- Trained a model, tuned one setting using only the validation set
- Evaluated the final model on the test set exactly once

## Key Takeaway
The test set should only be touched once, at the very end. If you tune
against it, you lose an honest estimate of real-world performance.

## Tools Used
Scikit-learn (`train_test_split`) • Pandas • Jupyter Notebook