# Human-AI Diagram: Cognitive Diversity Map

This diagram illustrates how different cognitive strategies influence how people engage with AI:  
analytical thinkers, intuitive thinkers, cautious evaluators, and speed-oriented operators.

```mermaid
flowchart TB

    subgraph Diversity
        A[Analytical Strategy]
        B[Intuitive Strategy]
        C[Cautious Strategy]
        D[Speed-Oriented Strategy]
    end

    subgraph AI_Interaction
        E[Explains Output]
        F[Presents Score]
        G[Shows Uncertainty]
    end

    subgraph Human_Response
        H[Interpretation]
        I[Confidence Shift]
        J[Decision Adjustment]
    end

    A --> E --> H
    B --> F --> I
    C --> G --> J
    D --> F --> J
