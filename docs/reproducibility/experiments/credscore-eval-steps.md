# CredScore — Evaluation Steps (Synthetic Demo)

This document explains the conceptual evaluation steps used for CredScore,
shown using *synthetic example data only*.  
It demonstrates how transparency, fairness, and stability checks were performed.

---

## 1. Input Dataset (Synthetic)
A minimal CSV with:

- applicant features  
- income, obligations, credit history signals  
- target label (good/bad outcome)

Example:

| income | age | credit_history | obligation_ratio | outcome |
|--------|-----|----------------|------------------|---------|
| 52000  | 34  | good           | 0.18             | good    |
| 41000  | 29  | limited        | 0.32             | bad     |

---

## 2. Feature Engineering Checks
Steps:

1. Validate feature scaling  
2. Check missing values  
3. Validate transformations (log, binning, normalization)

---

## 3. Model Evaluation
Two model families were evaluated:

- Gradient Boosting Model (GBM)
- Linear Model (interpretable baseline)

Metrics:

- AUC  
- F1-score  
- KS statistic  
- Stability Index (PSI)

---

## 4. Explainability Validation
Using SHAP on synthetic samples:

- global feature importance  
- sample-level reasoning  
- comparison between GBM and Linear model behaviour  

---

## 5. Fairness Exploration (Conceptual)
Simple subgroup comparisons (synthetic only):

- loan amount band  
- age group  
- income segments  

---

## 6. Reporting
Outputs generated:

- metrics table  
- SHAP summary  
- example explanations  
