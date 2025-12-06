# CredScore Diagram 1 — System Overview

This diagram shows the end to end flow of how CredScore processes applications,
extracts features, applies models, and produces explainable outputs.

---

```mermaid
flowchart TB

    subgraph INPUT [CredScore.Input Module]
        A1[Application Data]
        A2[Document Data]
        A3[Historical Records]
    end

    subgraph FE [CredScore.Feature Module]
        B1[Data Cleaning]
        B2[Feature Engineering]
        B3[Feature Scaling]
    end

    subgraph MODEL [CredScore.Model Module]
        C1[Gradient Boosted Model]
        C2[Linear Model]
        C3[Score Fusion]
    end

    subgraph EXPLAIN [CredScore.Explain Module]
        D1[SHAP Explanations]
        D2[LIME Explanations]
        D3[Summary Output]
    end

    A1 --> B1 --> B2 --> B3
    A2 --> B1
    A3 --> B1

    B3 --> C1 --> C3
    B3 --> C2 --> C3

    C3 --> D1 --> D2 --> D3
