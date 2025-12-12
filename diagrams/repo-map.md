# Repository Architecture Map

This Mermaid diagram provides a high-level visual overview of the structure of the `kishoredb-research` repository, including key documentation, diagrams, reproducibility artifacts, and portfolio metadata.

```mermaid

flowchart TB

%% Top-level

R[kishoredb-research (root)]

    R --> A[assets\n(images)]
    R --> B[datasets\n(README.md — empty)]
    R --> C[diagrams]
    R --> D[docs]
    R --> E[metadata\n(metadata.txt — empty)]
    R --> F[sample-data\n(sample-data.txt — empty)]
    R --> G[whitepapers\n(README.md)]
    R --> H[README.md]
    R --> I[CITATION.cff]
    R --> J[selected-works.md / .json]
    R --> K[supporting-works.md / .json]
    R --> L[publications.md / .json]
    R --> M[patents.md / .json]
    R --> N[talks.md / .json]
    R --> O[tech-projects.md / .json]
    R --> P[research-statement.md]
    R --> Q[domain-expertise.md]

    %% diagrams subtree (medium detail)
    C --> C1[aegis (diagrams)]
    C --> C2[credscore (diagrams)]
    C --> C3[fraud-engine (diagrams)]
    C --> C4[human-ai (diagrams)]
    C --> C5[methodology (diagrams)]
    C --> C6[smartcare (diagrams)]
    C --> C_README[diagrams/README.md]

    C1 --> C1a[aegis-architecture.md]
    C1 --> C1b[aegis-eval.md]
    C1 --> C1c[aegis-deploy.md]

    C2 --> C2a[credscore-architecture.md]
    C2 --> C2b[credscore-feature-pipeline.md]

    C3 --> C3a[fraud-engine-architecture.md]
    C3 --> C3b[fraud-engine-feature-pipeline.md]
    C3 --> C3c[fraud-engine-explainability-flow.md]

    C4 --> C4a[human-ai-transparency-loop.md]
    C4 --> C4b[cognitive-diversity-map.md]
    C4 --> C4c[trust-calibration-loop.md]

    C5 --> C5a[reproducibility-cycle.md]
    C5 --> C5b[transparency-pipeline.md]

    C6 --> C6a[smartcare-architecture.md]
    C6 --> C6b[smartcare-modeling-pipeline.md]

    %% docs subtree (medium detail)
    D --> D1[deep-dives]
    D --> D2[reproducibility]
    D --> D3[human-centered-ai.md]
    D --> D4[research-methodology.md]
    D --> D_README[docs/README.md]

    D1 --> D1a[aegis-deep-dive.md]
    D1 --> D1b[credscore-deep-dive.md]
    D1 --> D1c[fraud-engine-deep-dive.md]
    D1 --> D1d[smartcare-deep-dive.md]
    D1 --> D1e[cognitive-diversity-deep-dive.md]

    D2 --> D2a[configs\n(sample-config.yml)]
    D2 --> D2b[datasets\n(sample-*.csv, sample-schema.md)]
    D2 --> D2c[environment\n(python-environment.md)]
    D2 --> D2d[experiments\n(aegis-eval-steps.md, fraud-engine-eval-steps.md)]
    D2 --> D2e[reproducibility-guidelines.md]

    %% notes about empty/placeholder folders (visual)
    B --> B_note([note: folder currently empty — README.md placeholder])
    E --> E_note([note: metadata.txt placeholder — fill for automated ingestion])
    F --> F_note([note: sample-data placeholder — add example datasets])
