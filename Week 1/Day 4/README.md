# Day 4 — Pandas: Tabular Data

## Learning Objectives

- Load a real dataset into a DataFrame and inspect its structure
- Select columns and filter rows by condition
- Clean missing values and duplicates, and aggregate data with groupby

## What Was Done

- Loaded the Titanic dataset into a DataFrame and reported its shape, columns, and dtypes
- Counted and handled missing values (e.g., filled missing `Age` with the mean)
- Filtered the dataset to passengers older than 30
- Used `groupby("Pclass")` to compute average age and fare per passenger class, and interpreted the results

## Dataset

Titanic dataset (`train.csv`)

## Tools Used

Pandas • Jupyter Notebook