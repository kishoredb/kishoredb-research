# AEGIS Diagram 4 — Evaluation Pipeline

This diagram shows how AEGIS is evaluated end-to-end: from the evaluation dataset,
through STT and embedding quality checks, to search relevance benchmarks and a
human review loop that feeds back into pipeline and model improvements.

---

```mermaid
flowchart TB

    subgraph DATA [1. Evaluation Dataset]
        D[Evaluation Dataset]
    end

    subgraph COMPONENTS [2. Component Evaluation]
        STT[STT Accuracy Tests]
        EMB[Embedding Quality Checks]
        SEARCH[Search Ranking Benchmarks]
    end

    D --> STT
    D --> EMB
    D --> SEARCH

    subgraph METRICS [3. Metrics & Diagnostics]
        M1[WER / CER Metrics]
        M2[Embedding Similarity Metrics]
        M3[Precision@K / Recall@K]
    end

    STT --> M1
    EMB --> M2
    SEARCH --> M3

    subgraph REVIEW [4. Human Review Loop]
        H[Analyst / Reviewer Feedback]
        I[Pipeline and Model Improvements]
    end

    M1 --> H
    M2 --> H
    M3 --> H

    H --> I
