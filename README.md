# Give_Me_Some_Credit - Credit Risk Prediction

This project builds a machine learning model to predict the likelihood that a person will experience a serious financial delinquency within the next two years, based on the ["Give Me Some Credit"](https://www.kaggle.com/competitions/GiveMeSomeCredit) dataset from Kaggle.

---

## Dataset Overview

- Train Set: `cs-training.csv` (150,000 rows, labeled)
- Test Set: `cs-test.csv` (data only, no labels)
- Target Variable: `SeriousDlqin2yrs`  
    - `1` = serious delinquency  
    - `0` = no delinquency

---

## Features Used

| Feature                                 | Description                                        |
|-----------------------------------------|----------------------------------------------------|
| `RevolvingUtilizationOfUnsecuredLines`  | Ratio of credit card balance to limit              |
| `age`                                   | Age of the individual                              |
| `DebtRatio`                             | Total monthly debt payments to gross income ratio  |
| `MonthlyIncome`                         | Self-reported monthly income                       |
| `NumberOfOpenCreditLinesAndLoans`       | Open credit lines/loans (e.g., car, mortgage)      |
| `NumberOfTimes90DaysLate`               | Number of 90+ days late payments                   |
| `NumberRealEstateLoansOrLines`          | Real estate-related loans                          |
| `NumberOfTime30-59DaysPastDueNotWorse`  | 30-59 day delinquencies                            |
| `NumberOfTime60-89DaysPastDueNotWorse`  | 60-89 day delinquencies                            |
| `NumberOfDependents`                    | Number of dependents                               |

---

## Model Pipeline

1. Data Cleaning
    - Filled missing values with column medians
    - Removed ID column (`Unnamed: 0`)
2. Feature Preparation
    - Selected relevant features
3. Model
    - Random Forest Classifier (baseline)
4. Evaluation
    - Train-validation split (80-20)
    - Metrics: Accuracy, Precision, Recall, ROC AUC
5. Prediction
    - Predictions generated for the test set
    - Output file: `submission.csv`

---

## Model Evaluation (Validation Set)

| Metric        | Value       |
|---------------|-------------|
| Accuracy      | 85%         |
| Precision     | 25%         |
| Recall        | 57%         |
| ROC AUC Score | ~0.82       |

---

## Files in This Repo

| File                        | Description                                  |
|-----------------------------|----------------------------------------------|
| `cs-training.csv`           | Original training data (from Kaggle)         |
| `cs-testtest.csv`           | Original test data (from Kaggle)             |
| `Give_Me_Some_Credit.ipynb` | Jupyter Notebook with full pipeline          |
