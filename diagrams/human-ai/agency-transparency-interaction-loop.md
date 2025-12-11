# Human-AI Diagram: Agency–Transparency Interaction Loop

This diagram shows how transparency affects user agency, and how user feedback shapes future system transparency needs.

```mermaid
flowchart TB

    subgraph Transparency
        A[Explanation Quality]
        B[Uncertainty Display]
        C[Model Scope/Limit]
    end

    subgraph User_Agency
        D[Understanding]
        E[Sense of Control]
        F[Decision Ownership]
    end

    subgraph Feedback
        G[User Reaction]
        H[Trust Shift]
        I[Transparency Need Adjusted]
    end

    A --> D --> G
    B --> E --> H
    C --> F --> I
    I --> A
