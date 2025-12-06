```markdown
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
