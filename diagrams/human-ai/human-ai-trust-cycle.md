# Human-AI Diagram: Human–AI Trust Cycle

This diagram illustrates how trust is formed, challenged, and updated during AI-assisted work.

```mermaid
flowchart TB

    subgraph User
        A[Prior Experience]
        B[Initial Trust]
        C[Expectation]
    end

    subgraph AI_System
        D[AI Output]
        E[Explanation]
        F[Uncertainty Display]
    end

    subgraph Trust_Update
        G[Alignment Check]
        H[User Interpretation]
        I[Trust Increase/Decrease]
    end

    A --> B --> C --> D
    D --> E --> F
    F --> G --> H --> I
