# World Bank Poverty Prediction Challenge: Benchmarking ML Algorithms for Household Welfare Prediction

## Project Overview

This project uses my submission to the **World Bank Poverty Prediction Challenge** (hosted on DrivenData, November 2025 – February 2026) as a testbed for comparing the predictive performance of machine learning algorithms for household expenditure.

**Goal:** Evaluate how different modeling approaches perform when predicting household expenditure, particularly when trained on older survey data and applied to newer surveys.

## Background: The Challenge

Reliable poverty data are central to effective policymaking, but household consumption surveys — the standard tool for monetary poverty measurement — are costly and infrequent, leaving policymakers without timely information on household welfare, especially during periods of rapid economic change.

To address this gap, the World Bank launched the Poverty Prediction Challenge in November 2025: a global data science competition to advance methods for predicting household consumption and poverty across survey waves. The competition closed on February 4, 2026, with 1,322 registered participants and more than 500 valid solutions submitted.

**Task design (supervised learning):**
- Predict household-level expenditure from survey covariates (household size, education, employment, housing conditions, access to services, etc.)
- Participants could use any modeling approach: machine learning, classical econometrics, ensemble methods, or hybrids.

## My Approach

**Algorithms tested:**
- Linear Regression
- Ridge Regression
- Lasso Regression  
- Random Forest
- XGBoost

### Results
 
| Model | Train log R² ↑ | Train log MAE ↓ | Train log RMSE ↓ | Test log R² ↑ | Test log MAE ↓ | Test log RMSE ↓ | Test original R² ↑ | Test original MAE ↓ | Test original RMSE ↓ |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Linear regression | 0.63 | 0.31 | 0.40 | 0.64 | 0.31 | 0.40 | 0.51 | 3.45 | 6.13 |
| Ridge regression | 0.63 | 0.31 | 0.40 | 0.64 | 0.31 | 0.40 | 0.51 | 3.45 | 6.13 |
| Lasso regression | 0.63 | 0.31 | 0.40 | 0.64 | 0.31 | 0.40 | 0.51 | 3.45 | 6.13 |
| Random Forest (limited features) | 0.78 | 0.24 | 0.32 | 0.68 | 0.29 | 0.37 | 0.58 | 3.23 | 5.64 |
| XGBoost (limited features) | 0.71 | 0.28 | 0.36 | 0.68 | 0.29 | 0.37 | 0.60 | 3.21 | 5.53 |
| Random Forest (all available features) | 0.96 | 0.07 | 0.13 | 0.73 | 0.27 | 0.35 | 0.60 | 3.14 | 5.89 |
| XGBoost (all available features) | 0.79 | 0.23 | 0.30 | 0.75 | 0.26 | 0.33 | 0.65 | 3.03 | 5.52 |

## Repository Structure

```
├── data/                                   # Raw survey data
│   ├── feature_descriptions.csv
│   ├── feature_value_descriptions.csv
│   ├── test_hh_features.csv
│   ├── train_hh_features.csv
│   ├── df.pkl                             # saved from EDA.ipynb
├── scripts/                               # Python scripts
│   ├── EDA.ipynb                          # exploratory data analysis
│   ├── ML_algorithms.ipynb                # main script, testing predictive performance of different ML algorithms 
└── README.md
```

## Tools & Skills Demonstrated

- **Python**: data wrangling (`pandas`), machine learning (`scikit-learn`, `xgboost`)
- Model evaluation and cross-validation design considering stratification and sampling weights
- Applied prediction problem framed around real-world policy relevance (poverty measurement)

## About

This project builds on my background in applied econometrics and rural development economics, applying machine learning methods to a policy-relevant prediction problem.
