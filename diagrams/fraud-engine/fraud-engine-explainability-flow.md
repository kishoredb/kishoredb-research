# Fraud Engine Diagram 4 — Explainability Flow

This diagram shows how the Fraud Engine produces explainable outputs
based on rules, key features, and anomaly contributions.

---

```mermaid
flowchart TB

    subgraph INPUT [FraudEngine.ScoreInput Module]
        A1[Final Risk Score]
        A2[Feature Vector]
    end

    subgraph RULES [FraudEngine.RuleExplanation Module]
        B1[Triggered Rules]
        B2[Rule Descriptions]
    end

    subgraph SIGNALS [FraudEngine.SignalExplanation Module]
        C1[Top Contributing Features]
        C2[Anomaly Signal Breakdown]
    end

    subgraph OUTPUT [FraudEngine.ExplanationOutput Module]
        D1[Explainable Flags]
        D2[Human Readable Summary]
    end

    A1 --> B1 --> B2 --> D1
    A1 --> C1 --> C2 --> D2
    A2 --> C1
