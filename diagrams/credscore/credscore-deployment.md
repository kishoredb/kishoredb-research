# CredScore Diagram 5 — Deployment Flow

This diagram shows how CredScore is deployed in a cloud environment,
from API gateway intake to scoring services, explainability components,
and response delivery.

---

```mermaid
flowchart TB

    subgraph CLIENT [Client Layer]
        A1[Loan Origination System]
        A2[Credit Officer UI]
    end

    subgraph API [CredScore.API Module]
        B1[REST API Endpoint]
        B2[Auth Validation]
    end

    subgraph SCORE [CredScore.ScoringService Module]
        C1[Load Feature Vector]
        C2[Run GBM Model]
        C3[Run Linear Model]
        C4[Fuse Scores]
    end

    subgraph EXPLAIN [CredScore.ExplainService Module]
        D1[Generate SHAP Values]
        D2[Generate LIME Explanation]
        D3[Prepare Summary Output]
    end

    subgraph OUTPUT [CredScore.Response Module]
        E1[Final Score]
        E2[Explanation Package]
    end

    A1 --> B1 --> B2 --> C1 --> C2 --> C4 --> D1 --> D3 --> E2
    A2 --> B1
    C1 --> C3 --> C4
    D1 --> E2
    D2 --> D3
    C4 --> E1
