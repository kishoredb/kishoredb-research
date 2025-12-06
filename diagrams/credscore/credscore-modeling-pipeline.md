# CredScore Diagram 3 — Modeling Pipeline

This diagram shows how CredScore trains and evaluates multiple models,
combines their outputs, and produces a final risk score.

---

```mermaid
flowchart TB

    subgraph INPUT [CredScore.TrainingInput Module]
        A1[Feature Vector]
        A2[Training Labels]
    end

    subgraph MODELS [CredScore.ModelTraining Module]
        B1[Gradient Boosted Model Training]
        B2[Linear Model Training]
        B3[Validation Split]
    end

    subgraph SCORES [CredScore.ModelScores Module]
        C1[GBM Score]
        C2[Linear Score]
        C3[Score Fusion]
    end

    subgraph OUTPUT [CredScore.ScoreOutput Module]
        D1[Final Risk Score]
    end

    A1 --> B1 --> C1 --> C3 --> D1
    A1 --> B2 --> C2 --> C3
    A2 --> B3
