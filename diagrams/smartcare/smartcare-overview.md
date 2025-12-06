# SmartCare Diagram 1 — System Overview

This diagram shows how SmartCare processes patient observations,
applies rule based reasoning, generates early warnings,
and supports caregiver decision making.

---

```mermaid
flowchart TB

    subgraph INPUT [SmartCare.Input Module]
        A1[Patient Observations]
        A2[Caregiver Notes]
        A3[Medical History]
    end

    subgraph FE [SmartCare.Feature Module]
        B1[Data Normalization]
        B2[Symptom Extraction]
        B3[Pattern Detection]
    end

    subgraph RULES [SmartCare.RuleEngine Module]
        C1[Rule Evaluation]
        C2[Severity Assessment]
        C3[Risk Categorization]
    end

    subgraph OUTPUT [SmartCare.Output Module]
        D1[Early Warning Signal]
        D2[Caregiver Recommendation]
    end

    A1 --> B1 --> B2 --> B3 --> C1 --> C2 --> C3 --> D1
    A2 --> B1
    A3 --> B1
    C3 --> D2
