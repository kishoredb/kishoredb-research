# Human-AI Diagram: Explanation Processing Model

This diagram shows how users process, evaluate, and act on explanations from AI systems.

```mermaid
flowchart TB

    subgraph Input
        A[AI Output]
        B[Explanation Provided]
    end

    subgraph Cognitive_Process
        C[Comprehension]
        D[Relevance Check]
        E[Uncertainty Interpretation]
        F[Actionability Assessment]
    end

    subgraph Outcome
        G[Decision Made]
        H[Override or Accept]
        I[Learning Feedback]
    end

    A --> B --> C --> D --> E --> F --> G --> H --> I
