# Explanation Misalignment Flow

This diagram shows why AI explanations sometimes fail to support human understanding.
Misalignment occurs when the explanation provided does not match the user’s
mental model, cognitive needs, or context.

```mermaid
flowchart TB

    A[AI Internal Reasoning] --> B[Generated Explanation]
    C[User Mental Model] --> D[User Interpretation]

    B --> E[Explanation Received]
    D --> F[Meaning Constructed]

    E --> G{Alignment Check}
    F --> G

    G -->|Aligned| H[Correct Understanding]
    G -->|Misaligned| I[Confusion or Incorrect Action]

    I --> J[Reduced Trust or Overrides]
