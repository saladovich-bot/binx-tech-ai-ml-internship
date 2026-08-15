# Data Dictionary — cardiac_synthetic.csv

This dataset is **synthetic**, generated from a hand-designed cardiac risk formula. It is used for educational purposes only and does not represent real patient data.

| Column | Type | Description |
|---|---|---|
| `age` | numeric | Patient's age, in years |
| `sex` | categorical | Patient's sex — `male` / `female` |
| `chest_pain_type` | categorical | Type of chest pain reported (e.g. `asymptomatic`, `non_anginal`, etc.) |
| `resting_bp` | numeric | Resting blood pressure, in mm Hg |
| `cholesterol` | numeric | Serum cholesterol level, in mg/dl |
| `fasting_bs_high` | binary (0/1) | Whether fasting blood sugar is above 120 mg/dl (`1` = high, `0` = normal) |
| `resting_ecg` | categorical | Resting electrocardiogram result (e.g. `normal`, etc.) |
| `max_heart_rate` | numeric | Maximum heart rate achieved during exercise, in beats per minute |
| `exercise_angina` | categorical | Whether exercise induced angina — `yes` / `no` |
| `oldpeak` | numeric | ST depression induced by exercise relative to rest |
| `heart_disease` | binary (0/1) | **Target variable** — `1` = disease present, `0` = no disease |

## Engineered Features (created during feature engineering, not in raw CSV)

| Column | Type | Description |
|---|---|---|
| `hr_bp_ratio` | numeric | `max_heart_rate` ÷ `resting_bp` — a combined measure of cardiovascular response |
| `age_group` | categorical | `age` binned into `under_40`, `40_54`, `55_69`, `70_plus` |
