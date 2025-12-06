# AEGIS Diagram 4 — Evaluation Pipeline

This diagram shows how AEGIS is evaluated end-to-end: from test data selection, through
STT and embedding quality checks, to search relevance benchmarks and human review.
It highlights that AEGIS is treated as a research system, not just an engineering artifact.

---

```mermaid
flowchart TB

    %% ---------------------------
    %% 1. Input: Evaluation Data
    %% ---------------------------
    subgraph DATA [1. Evaluation Dataset]
        direction TB
        D[Curated Test Set<br/>(Videos + Ground Truth)]
    end

    %% ---------------------------
    %% 2. Component-Level Evaluation
    %% ---------------------------
    subgraph COMPONENTS [2. Component Evaluation]
        direction TB
        STT[STT Accuracy Tests<br/>(WER / CER)]
        EMB[Embedding Quality Checks<br/>(Similarity / Clustering)]
        SEARCH[Search Ranking Benchmarks<br/>(Precision@K / Recall@K)]
    end

    D --> STT
    D --> EMB
    D --> SEARCH

    %% ---------------------------
    %% 3. Metrics & Diagnostics
    %% ---------------------------
    subgraph METRICS [3. Metrics & Diagnostics]
        direction TB
        M1[STT Metrics<br/>WER / CER]
        M2[Embedding Metrics<br/>Similarity Distributions]
        M3[Search Metrics<br/>Precision@K / Recall@K]
    end

    STT --> M1
    EMB --> M2
    SEARCH --> M3

    %% ---------------------------
    %% 4. Human Review Loop
    %% ---------------------------
    subgraph REVIEW [4. Human Review Loop]
        direction TB
        H[Analyst / Reviewer Feedback<br/>(Qualitative Judgement)]
        I[Pipeline & Model Improvements]
    end

    M1 --> H
    M2 --> H
    M3 --> H

    H --> I
