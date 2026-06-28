# Credit Risk Analytics in R

R-based credit risk modelling pipeline covering WoE/IV, PD scorecard development, Kaplan-Meier survival curves, and ECL computation under Ind AS 109. Built from scratch using synthetic retail lending data.

> Built alongside the **Credit Risk Analytics** elective | GIM BDA Term 4 (2025–26)

---

## Topics Covered

| Day | File | Topics |
|-----|------|---------|
| 1 | `01_basics_data_gen.R` | R basics, data types, data frames, synthetic loan data generation |
| 2 | *(upcoming)* | Exploratory Data Analysis (EDA) |
| 3 | *(upcoming)* | Weight of Evidence (WoE) & Information Value (IV) |
| 4 | *(upcoming)* | Logistic Regression — PD modelling |
| 5 | *(upcoming)* | Model Evaluation — KS, Gini, AUC, Scorecard |
| 6 | *(upcoming)* | Survival Analysis — Kaplan-Meier, Cox PH |
| 7 | *(upcoming)* | ECL Modelling — PD × LGD × EAD, Ind AS 109 |

---

## Files

```
credit-risk-analytics-r/
│
├── data/
│   └── synthetic_loan_data.csv      # generated in Day 1
│
├── 01_basics_data_gen.R             # Day 1
├── 02_eda.R                         # Day 2 (upcoming)
├── 03_woe_iv.R                      # Day 3 (upcoming)
├── 04_logistic_regression.R         # Day 4 (upcoming)
├── 05_model_evaluation.R            # Day 5 (upcoming)
├── 06_survival_analysis.R           # Day 6 (upcoming)
└── 07_ecl_modelling.R               # Day 7 (upcoming)
```

---

## What I Learned — Day 1

- R vectors, factors, and data frames as the foundation for tabular credit data
- Why `factor()` matters early — needed for WoE/IV binning and logistic regression encoding
- Synthetic data generation using `rnorm()`, `rbinom()`, and `pmin()`/`pmax()` for realistic clamping
- Embedding a logistic default-generation mechanism (sigmoid on credit score + DTI + delinquencies) so the dataset has learnable signal from Day 1
- `tapply()` for quick group-level default rate checks before any formal modelling

---

## Key Takeaways

- Default rate in the synthetic dataset: ~17–20% (realistic for retail lending in India)
- Credit score is the strongest single predictor — default rate in "Very Poor" band (~2x the "Good" band)
- Self-Employed borrowers show higher default probability by design — mirrors real-world underwriting logic
- `set.seed(42)` is non-negotiable for reproducibility across sessions

---

## Next Steps

- Day 2: Full EDA — distributions, missing value analysis, correlation heatmap, default rate plots
- Packages to install: `ggplot2`, `dplyr`, `skimr`, `corrplot`

---

## Setup

```r
# No external packages needed for Day 1
# Run the script end-to-end; dataset auto-saves to data/
source("01_basics_data_gen.R")
```

---

## Author

**Prajwal Vijay Nikhar** | MBA – Big Data Analytics | Goa Institute of Management
