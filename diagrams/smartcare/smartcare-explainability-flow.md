# SmartCare Diagram 4 — Explainability Flow

This diagram shows how SmartCare produces transparent explanations
for caregivers using rule triggers and symptom contributions.

---

```mermaid
flowchart TB

    subgraph INPUT [SmartCare.ExplainInput Module]
        A1[Risk Level]
        A2[Feature Vector]
    end

    subgraph RULES [SmartCare.RuleExplain Module]
        B1[Triggered Rules]
        B2[Rule Descriptions]
    end

    subgraph SIGNALS [SmartCare.SymptomExplain Module]
        C1[Key Symptoms]
        C2[Trend Contribution]
    end

    subgraph OUTPUT [SmartCare.ExplanationOutput Module]
        D1[Explainable Summary]
        D2[Guidance For Caregivers]
    end

    A1 --> B1 --> B2 --> D1
    A1 --> C1 --> C2 --> D2
    A2 --> C1
