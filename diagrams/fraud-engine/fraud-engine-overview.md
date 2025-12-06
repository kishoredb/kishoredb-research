# Fraud Engine Diagram 1 — System Overview

This diagram shows how the Fraud Engine processes incoming transactions,
extracts features, applies hybrid models, and produces real time risk signals.

---

```mermaid
flowchart TB

    subgraph INPUT [FraudEngine.Input Module]
        A1[Transaction Stream]
        A2[Customer Profile]
        A3[Historical Patterns]
    end

    subgraph FE [FraudEngine.Feature Module]
        B1[Data Normalization]
        B2[Time Series Features]
        B3[NLP Metadata Features]
    end

    subgraph MODEL [FraudEngine.Model Module]
        C1[Anomaly Model]
        C2[Rule Engine]
        C3[Score Fusion]
    end

    subgraph OUTPUT [FraudEngine.Output Module]
        D1[Risk Score]
        D2[Risk Flags]
    end

    A1 --> B1 --> B2 --> B3 --> C1 --> C3 --> D1
    A2 --> B1
    A3 --> B1
    C2 --> C3 --> D2
