# Transparency & Explainability Pipeline  
A structured view of how raw system behaviour is converted into human-understandable explanations.

---

```mermaid
flowchart TB

    subgraph INPUTS [1. Model Inputs & Features]
        A1[Raw Data]
        A2[Feature Engineering]
        A3[Domain Rules]
    end

    subgraph MODEL [2. Model Behaviour]
        B1[Predictions]
        B2[Uncertainty Scores]
        B3[Intermediate Signals]
    end

    subgraph EXPLAIN [3. Explanation Layer]
        C1[SHAP / LIME]
        C2[Rule-Based Reason Codes]
        C3[Counterfactual Examples]
    end

    subgraph HUMAN [4. Human Interpretation]
        D1[Plain-Language Summaries]
        D2[Decision Support Views]
        D3[Override Notes]
    end

    INPUTS --> MODEL --> EXPLAIN --> HUMAN
