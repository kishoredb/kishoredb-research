# CredScore Diagram 2 — Feature Pipeline

This diagram shows how CredScore processes input data into clean, usable,
model-ready features. It includes cleaning, imputation, transformation,
and feature generation steps in a linear and stable flow.

---

```mermaid
flowchart TB

    subgraph INPUT [CredScore.Input Module]
        A1[Raw Application Data]
        A2[Document Fields]
        A3[Bureau Data]
    end

    subgraph CLEAN [CredScore.Cleaning Module]
        B1[Schema Validation]
        B2[Missing Value Handling]
        B3[Outlier Checks]
    end

    subgraph TRANSFORM [CredScore.Transform Module]
        C1[Encoding]
        C2[Scaling]
        C3[Derived Features]
    end

    subgraph OUTPUT [CredScore.FeatureOutput Module]
        D1[Feature Vector]
    end

    A1 --> B1 --> B2 --> B3 --> C1 --> C2 --> C3 --> D1
    A2 --> B1
    A3 --> B1
