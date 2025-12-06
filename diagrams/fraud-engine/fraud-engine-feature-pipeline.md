# Fraud Engine Diagram 2 — Feature Pipeline

This diagram shows how the Fraud Engine transforms raw events into
model-ready features using time series signals, metadata extraction,
and contextual information.

---

```mermaid
flowchart TB

    subgraph INPUT [FraudEngine.Input Module]
        A1[Raw Transaction]
        A2[Customer Metadata]
        A3[Historical Window]
    end

    subgraph CLEAN [FraudEngine.Cleaning Module]
        B1[Schema Validation]
        B2[Missing Value Checks]
        B3[Deduplication]
    end

    subgraph TRANSFORM [FraudEngine.Transform Module]
        C1[Time Window Aggregates]
        C2[NLP Tag Extraction]
        C3[Derived Risk Features]
    end

    subgraph OUTPUT [FraudEngine.FeatureOutput Module]
        D1[Feature Vector]
    end

    A1 --> B1 --> B2 --> B3 --> C1 --> C2 --> C3 --> D1
    A2 --> B1
    A3 --> B1
