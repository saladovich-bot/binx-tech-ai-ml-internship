# Cardiac Patient Monitoring System — AI & ML Individual Project

**BinX Tech — AI & Machine Learning Track**

## Project Objective

This project builds a curriculum-aligned machine learning analysis on a **synthetic** cardiac dataset. It cleans and explores the data, trains and compares supervised classification models, evaluates them with cross-validation and standard metrics, and applies feature engineering with a leak-free Scikit-learn Pipeline.

## Project Structure

```
├── cardiac_project.ipynb   # main notebook (run top to bottom)
├── data/cardiac_synthetic.csv
├── requirements.txt
└── README.md
```

## How to Run

1. Create and activate a virtual environment:
   ```
   python -m venv venv
   venv\Scripts\activate      # Windows
   source venv/bin/activate   # macOS/Linux
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Open `cardiac_project.ipynb` in Jupyter Notebook or VS Code.
4. Run the notebook top to bottom (`Kernel -> Restart & Run All`). No manual/hidden steps are required.

## Summary of Results

- The Logistic Regression baseline outperformed the Random Forest comparison model on test accuracy, cross-validated F1, and ROC-AUC.
- Feature engineering (`hr_bp_ratio`, `age_group`) plus `GridSearchCV` tuning on Logistic Regression gave a further, modest improvement over the untuned baseline (F1: 0.677 → 0.710).

## Limitations

- The dataset is **synthetic**, generated from a hand-designed risk formula — results describe how well the models recover that formula's pattern, not real-world cardiac risk.
- No deep learning, external APIs, or production deployment were used, per the project's stated scope.
- This project is for educational purposes only and must not be used for actual clinical diagnosis or treatment decisions.
