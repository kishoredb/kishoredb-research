# Repository Architecture Map

This Mermaid diagram provides a high-level visual overview of the structure of the `kishoredb-research` repository, including key documentation, diagrams, reproducibility artifacts, and portfolio metadata.

```mermaid

flowchart LR

    R[kishoredb-research]

    %% Top-level folders (vertical)
    R --> A[assets]
    R --> B[datasets]
    R --> C[diagrams]
    R --> D[docs]
    R --> E[metadata]
    R --> F[sample-data]
    R --> G[whitepapers]

    %% Top-level files
    R --> H[README.md]
    R --> I[CITATION.cff]
    R --> J[selected-works.md]
    R --> K[supporting-works.md]
    R --> L[publications.md]
    R --> M[patents.md]
    R --> N[talks.md]
    R --> O[tech-projects.md]
    R --> P[research-statement.md]
    R --> Q[domain-expertise.md]

    %% diagrams subtree
    C --> C1[aegis]
    C --> C2[credscore]
    C --> C3[fraud-engine]
    C --> C4[human-ai]
    C --> C5[methodology]
    C --> C6[smartcare]

    %% docs subtree
    D --> D1[deep-dives]
    D --> D2[reproducibility]
    D --> D3[human-centered-ai.md]
    D --> D4[research-methodology.md]
