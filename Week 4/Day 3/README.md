# Day 3 — Bias-Variance & Diagnosing Model Fit

## Overview
Today I learned how to diagnose whether a model is underfitting or
overfitting, and how regularization fixes overfitting.

## What I Did
- Deliberately overfit a model and observed the large train-vs-validation
  score gap
- Deliberately underfit a model and observed low scores on both sets
- Applied regularization (Ridge / Lasso) to the overfit model and
  observed the gap shrink
- Documented each diagnosis with score evidence

## Key Takeaway
The gap between training and validation scores is the main diagnostic
tool: low/low means underfitting, high/much-lower means overfitting,
and high/high (small gap) is the target.

## Tools Used
Scikit-learn (Ridge, Lasso, DecisionTree) • Pandas • Matplotlib • Jupyter Notebook