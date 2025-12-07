# Reproducibility Cycle  
A workflow showing how experiments remain stable, auditable, and repeatable across environments.

---

```mermaid
flowchart TB

    subgraph VERSIONING [1. Version Everything]
        A1[Data Versions]
        A2[Model Versions]
        A3[Config Versions]
    end

    subgraph ENV [2. Isolated Execution]
        B1[Containerized Environments]
        B2[Dependency Locks]
    end

    subgraph RUN [3. Deterministic Runs]
        C1[Seed Control]
        C2[Automated Pipelines]
    end

    subgraph LOGS [4. Transparent Logging]
        D1[Experiment Logs]
        D2[Metrics Snapshots]
    end

    subgraph REVIEW [5. Peer + Human Review]
        E1[Repeat Experiments]
        E2[Validate Outcomes]
    end

    subgraph IMPROVE [6. Model & Pipeline Improvements]
        F1[Refine Features]
        F2[Fix Drift]
    end

    VERSIONING --> ENV --> RUN --> LOGS --> REVIEW --> IMPROVE --> VERSIONING
