# Cognitive Load Flow

This diagram illustrates how cognitive load builds or reduces during AI-assisted decision-making. 

It highlights where complexity, ambiguity, or poor explanation quality can overload users.

```mermaid
flowchart TB

    A[Task Input] --> B[AI Suggestion or Explanation]
    B --> C[User Processing Effort]
    C --> D{Cognitive Load Level}

    D -->|Low Load| E[Efficient Decision]
    D -->|Medium Load| F[Slowed Reasoning]
    D -->|High Load| G[Overload or Error]

    G --> H[Workarounds or System Avoidance]
