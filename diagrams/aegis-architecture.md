```mermaid
flowchart TD

    A1[Upload Video]
    A2[Extract Audio (FFmpeg)]
    A3[Transcribe (Whisper / Azure STT)]
    A4[Clean Transcript]
    A5[Chunk + Timestamps]
    A6[Create Embeddings (BERT/GPT)]
    A7[Store Transcript (CosmosDB)]
    A8[Store Vectors (Azure Search)]

    Q1[User Query]
    Q2[Query Embedding]
    Q3[Semantic Search]
    Q4[Matched Segments]
    Q5[Jump to Timestamp]

    A1 --> A2 --> A3 --> A4 --> A5 --> A6
    A6 --> A7
    A6 --> A8

    Q1 --> Q2 --> Q3 --> Q4 --> Q5
```
