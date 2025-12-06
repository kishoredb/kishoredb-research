Aegis Diagram 1 — End-to-End Architecture Overview
This diagram shows the whole system at once, from video input → transcript → embeddings → index → search → playback.
flowchart LR
    A[Video File] --> B[Audio Extraction (FFmpeg)]
    B --> C[Speech-to-Text (Whisper / Azure STT)]
    C --> D[Transcript Cleanup & Normalization]

    D --> E1[Sentence Splitting]
    E1 --> E2[Embedding Creation (BERT / GPT)]
    
    D --> F1[Transcript Storage (CosmosDB)]
    E2 --> F2[Vector Index Storage (Azure Search)]

    G[User Query] --> H[Query Embedding Creation]
    H --> I[Vector Similarity Search]
    I --> J[Ranked Segments]

    J --> K[Timestamp Retrieval]
    K --> L[Video Player]

    F1 -.-> I
    F2 -.-> I
