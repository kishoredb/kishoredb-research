# CredScore Diagram 4 — Explainability Flow

This diagram shows how CredScore generates transparent, human-understandable
explanations for its risk score using SHAP, LIME, and summary outputs.

---

```mermaid
flowchart TB

    subgraph INPUT [CredScore.ScoreInput Module]
        A1[Final Risk Score]
        A2[Feature Vector]
    end

    subgraph SHAP [CredScore.SHAP Module]
        B1[Compute SHAP Values]
        B2[SHAP Feature Ranking]
    end

    subgraph LIME [CredScore.LIME Module]
        C1[Local Perturbation]
        C2[LIME Local Explanation]
    end

    subgraph SUMMARY [CredScore.ExplanationOutput Module]
        D1[Top Drivers]
        D2[Human Readable Summary]
        D3[Audit Friendly Output]
    end

    A1 --> B1 --> B2 --> D1
    A1 --> C1 --> C2 --> D2
    A2 --> B1
    A2 --> C1
    D1 --> D3
    D2 --> D3
