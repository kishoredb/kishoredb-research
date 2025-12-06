# AEGIS Diagram 4 — Evaluation Pipeline

This diagram presents the evaluation process used to assess the performance of AEGIS’s 
speech recognition, embedding quality, search ranking, and human-review validation. 

Including this diagram demonstrates research rigor and helps reviewers understand how 
system quality was measured.

---

```mermaid
flowchart TB

    A[Evaluation Dataset] --> B[STT Accuracy Tests]
    A --> C[Embedding Similarity Validation]
    A --> D[Search Ranking Benchmarks]

    B --> E[WER / CER Scores]
    C --> F[Cosine Similarity Distribution]
    D --> G[Precision@K / Recall@K]

    E --> H[Human Review Loop]
    F --> H
    G --> H

    H --> I[Pipeline / Model Improvements]
