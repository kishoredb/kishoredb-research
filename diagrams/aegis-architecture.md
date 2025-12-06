flowchart TB
    subgraph EvalData
        ED[Evaluation dataset]
    end

    subgraph ComponentTests
        STT[STT accuracy tests]
        EMB[Embedding quality checks]
        SRCH[Search ranking benchmarks]
    end

    ED --> STT
    ED --> EMB
    ED --> SRCH

    subgraph Metrics
        M1[WER / CER metrics]
        M2[Embedding similarity metrics]
        M3[Precision@K / Recall@K]
    end

    STT --> M1
    EMB --> M2
    SRCH --> M3

    subgraph HumanReview
        HR[Human review & feedback]
        IMP[Pipeline / model improvements]
    end

    M1 --> HR
    M2 --> HR
    M3 --> HR
    HR --> IMP
