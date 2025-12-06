# Fraud Engine Diagram 5 — Deployment Flow

This diagram shows how the Fraud Engine operates in real time,
from event intake to scoring to alert generation.

---

```mermaid
flowchart TB

    subgraph INPUT [Event Intake Layer]
        A1[Event Stream]
        A2[API Gateway]
    end

    subgraph PROCESS [FraudEngine.ProcessingService Module]
        B1[Event Parsing]
        B2[Feature Lookup]
        B3[Model Execution]
        B4[Rule Evaluation]
    end

    subgraph OUTPUT [FraudEngine.AlertOutput Module]
        C1[Risk Score]
        C2[Fraud Alert]
    end

    A1 --> B1 --> B2 --> B3 --> B4 --> C1
    A2 --> B1
    B4 --> C2
