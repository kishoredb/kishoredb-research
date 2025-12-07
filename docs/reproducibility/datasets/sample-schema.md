# Synthetic Dataset Schemas (For Reproducibility Examples)

These schemas illustrate the structure of datasets used in the deep-dives.

---

## Credit Scoring (Synthetic)
| field | type | description |
|-------|------|-------------|
| income | float | annual income |
| age | int | applicant age |
| credit_history | int | months of credit history |
| delinquency_count | int | number of late payments |
| label | int | 1 = approved, 0 = rejected |

---

## Fraud Detection (Synthetic)
| field | type | description |
|-------|------|-------------|
| txn_amount | float | transaction amount |
| merchant_category | string | MCC code |
| timestamp | datetime | transaction time |
| risk_score | float | ML risk score |
| is_fraud | int | 0/1 |

---

## Aegis (Synthetic Metadata)
```json
{
  "video_id": "demo001",
  "duration": 1260,
  "segments": [
    {"start": 0, "end": 30, "text": "Welcome introduction."},
    {"start": 30, "end": 75, "text": "Topic overview of system design."}
  ]
}

