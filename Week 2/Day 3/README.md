# Day 3 — Linear Algebra for ML

## Learning Objectives

- Represent data samples as vectors and datasets as matrices
- Compute a dot product and explain why it is central to model prediction
- Perform matrix multiplication and reason about resulting shapes

## What Was Done

- Represented three data samples as a (3 × features) NumPy matrix
- Computed the dot product of one sample vector with a weight vector by hand, then verified it with `np.dot`
- Used matrix multiplication (`@`) to produce predictions for all three samples at once
- Deliberately triggered a shape-mismatch error, read the message, and explained in Markdown why it occurred and how to fix it

## Dataset

Custom sample data (age, income, tenure features) — no external dataset used

## Tools Used

NumPy • Jupyter Notebook