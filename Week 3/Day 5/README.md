# Day 5 — Supervised-Learning Mini-Project

## Learning Objectives

- Assemble a complete supervised-learning pipeline from EDA to evaluation
- Apply basic preprocessing (encoding, scaling) without data leakage
- Select and justify an appropriate model and metric for the task, and document the result

## Task

**Type:** Classification — the target column (`Churn`) has two values, `Yes` / `No`, so this is a binary classification problem, not regression.

**Goal:** Predict whether a telecom customer will churn (leave the company) based on their account and service data.

## Dataset

[Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) (`WA_Fn-UseC_-Telco-Customer-Churn.csv`) — 7,043 customers, 21 columns covering demographics, account info (tenure, contract, payment method), subscribed services (phone, internet, streaming, security, backup, etc.), and monthly/total charges.

## What Was Done

### 1. Data Cleaning
- Checked for missing values with `df.isnull().sum()`
- Filled missing `Partner` values with the column mode, and missing `MonthlyCharges` with the median
- Converted `TotalCharges` from object to numeric (`pd.to_numeric`, `errors="coerce"`), which revealed hidden blank strings as `NaN`, then filled them with the median
- Checked for duplicate rows (`df.duplicated().sum()`) — none found

### 2. Exploratory Data Analysis
- `gender` distribution: roughly balanced between male and female (~3,500 each)
- `TotalCharges` distribution: right-skewed, most customers have `TotalCharges < 500`
- Checked `TotalCharges` for outliers using the IQR method — none found
- `MonthlyCharges` vs `tenure`: no clear linear relationship, points scattered broadly
- `MonthlyCharges` vs `TotalCharges`: positive but non-linear relationship (triangular scatter shape) — consistent with `TotalCharges ≈ MonthlyCharges × tenure`, meaning `TotalCharges` depends on both monthly rate and how long the customer has been subscribed

### 3. Encoding
- Binary Yes/No and Male/Female columns (`gender`, `Partner`, `Dependents`, `PhoneService`, `PaperlessBilling`, `Churn`) mapped to 1/0
- Service-dependent columns (`MultipleLines`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`) mapped to 1/0, with `"No phone/internet service"` folded into `0` — since `PhoneService`/`InternetService` already capture that information, no signal is lost
- Multi-category columns (`InternetService`, `Contract`, `PaymentMethod`) one-hot encoded with `pd.get_dummies`
- `customerID` dropped before modeling (identifier, not a feature)

### 4. Train/Test Split & Scaling
- 80/20 split with `train_test_split(..., random_state=42)`
- `StandardScaler` fit on `X_train` only, then applied to `X_test` — avoids data leakage from the test set

### 5. Modeling
Trained three classifiers plus a baseline, all on the same scaled train/test split:

| Model | F1-score (Churn = Yes) |
|---|---|
| **Logistic Regression** | **0.640** |
| Random Forest (100 trees) | 0.546 |
| k-NN (k=5) | 0.542 |
| Baseline (`DummyClassifier`, most frequent) | 0.000 |

### 6. Model Selection
Since the business goal is identifying customers who will actually leave, the F1-score for the **positive class (Churn = Yes)** was used to compare models, not overall accuracy. The baseline scores 0.00 on this metric — it always predicts "No churn" and never catches a single churner, despite ~74% overall accuracy, which shows why accuracy alone would be misleading here.

**Logistic Regression was selected as the final model**, with the best F1-score (0.64) for the churn class, outperforming Random Forest (0.546) and k-NN (0.542).

## Tools Used

Scikit-learn (LogisticRegression, RandomForestClassifier, KNeighborsClassifier, DummyClassifier, StandardScaler, train_test_split, classification_report, f1_score) • Pandas • NumPy • Matplotlib • Seaborn • Jupyter Notebook