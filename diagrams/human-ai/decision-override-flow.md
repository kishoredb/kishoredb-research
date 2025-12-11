# Human-AI Diagram: Decision Override Flow

This diagram shows when and how users override AI recommendations in high-stakes workflows.

```mermaid
flowchart TB

    subgraph AI_Output
        A[AI Suggestion]
        B[Reason or Score]
    end

    subgraph User_Check
        C[Expectation Check]
        D[Risk Assessment]
        E[Confidence Evaluation]
    end

    subgraph Decision_Path
        F[Accept Suggestion]
        G[Override Suggestion]
        H[Request More Info]
    end

    A --> B --> C --> D --> E

    E --> F
    E --> G
    E --> H
