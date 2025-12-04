# CredScore — Explainable Credit Scoring System  
**Architecture Diagram**

This document presents the architecture of CredScore, an explainable credit risk  
scoring system designed for regulated lending environments.  
The system integrates ML models, a rule engine, and an explanation layer to  
produce transparent, auditable credit decisions.

---

## Architecture Diagram

```mermaid
flowchart LR
    D1[Core Banking Data]
    D2[Credit Bureau Data]
    D3[Loan Application Data]

    D1 --> FE[Feature Engineering Layer]
    D2 --> FE
    D3 --> FE

    FE --> MODEL[ML Models<br/> - GBM<br/> - Logistic Regression]
    MODEL --> EXPL[Explainability Engine<br/>SHAP / LIME]
    FE --> RULES[Rule / Policy Engine]

    MODEL --> SCORE[Credit Score Service]
    RULES --> SCORE
    EXPL --> SCORE

    SCORE --> LOS[Loan Origination System]
    SCORE --> REVIEW[Underwriter / Risk Review UI]
---
```
---

## Notes  
- Combines **ML-based scoring** with **rule-based overrides** for compliance.  
- Explainability engine produces **SHAP/LIME-based insights** for transparency.  
- Outputs integrate with **Loan Origination Systems (LOS)** and **risk review dashboards**.  

