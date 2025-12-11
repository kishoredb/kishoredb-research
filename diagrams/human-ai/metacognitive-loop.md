# Human-AI Diagram: Metacognitive Loop

This diagram shows how humans monitor, evaluate, and adjust decisions while interacting with AI suggestions.

```mermaid
flowchart TB

    subgraph Perception
        A[Task Input]
        B[Initial Interpretation]
        C[Initial Confidence]
    end

    subgraph AI_Assist
        D[AI Suggestion]
        E[AI Confidence/Score]
    end

    subgraph Metacognition
        F[Monitoring]
        G[Comparing Expectation vs AI]
        H[Confidence Recalibration]
        I[Decision Adjustment]
    end

    A --> B --> C --> D
    D --> E
    E --> F --> G --> H --> I
