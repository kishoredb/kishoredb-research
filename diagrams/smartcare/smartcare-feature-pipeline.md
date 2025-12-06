# SmartCare Diagram 2 — Feature Pipeline

This diagram shows how SmartCare transforms raw patient inputs
into structured representations for rule evaluation.

---

```mermaid
flowchart TB

    subgraph INPUT [SmartCare.Input Module]
        A1[Raw Observations]
        A2[Vital Signs]
        A3[Symptom Notes]
    end

    subgraph CLEAN [SmartCare.Cleaning Module]
        B1[Data Validation]
        B2[Missing Value Handling]
        B3[Noise Reduction]
    end

    subgraph TRANSFORM [SmartCare.Transform Module]
        C1[Symptom Encoding]
        C2[Trend Analysis]
        C3[Derived Health Features]
    end

    subgraph OUTPUT [SmartCare.FeatureOutput Module]
        D1[Feature Vector]
    end

    A1 --> B1 --> B2 --> B3 --> C1 --> C2 --> C3 --> D1
    A2 --> B1
    A3 --> B1
