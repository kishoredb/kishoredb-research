# AEGIS Diagram 4 — Evaluation Pipeline

This diagram shows how AEGIS is evaluated end-to-end: from the evaluation dataset,
through STT and embedding quality checks, to search relevance benchmarks and a
human review loop that feeds back into pipeline and model improvements.

---

```mermaid
flowchart TB

    subgraph DATA [AEGIS.EvalData Module]
        D1[Evaluation Dataset]
    end

    subgraph TESTS [AEGIS.ComponentTests Module]
        T1[STT Accuracy Tests]
        T2[Embedding Quality Checks]
        T3[Search Ranking Benchmarks]
    end

    subgraph METRICS [AEGIS.Metrics Module]
        M1[WER And CER Scores]
        M2[Embedding Similarity Scores]
        M3[Precision At K Metrics]
    end

    subgraph REVIEW [AEGIS.Review Module]
        R1[Human Review Feedback]
        R2[Pipeline Improvements]
    end

    D1 --> T1 --> M1 --> R1 --> R2
    D1 --> T2 --> M2 --> R1
    D1 --> T3 --> M3 --> R1
