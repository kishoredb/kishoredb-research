# SmartCare Diagram 3 — Rule Evaluation Pipeline

This diagram shows how SmartCare evaluates symptoms,
applies rules, and generates severity scores.

---

```mermaid
flowchart TB

    subgraph INPUT [SmartCare.RuleInput Module]
        A1[Feature Vector]
        A2[Care Guidelines]
    end

    subgraph RULES [SmartCare.RuleEngine Module]
        B1[Condition Matching]
        B2[Rule Scoring]
        B3[Severity Calculation]
    end

    subgraph OUTPUT [SmartCare.RuleOutput Module]
        C1[Risk Level]
        C2[Recommended Action]
    end

    A1 --> B1 --> B2 --> B3 --> C1
    A2 --> B1
    C1 --> C2
