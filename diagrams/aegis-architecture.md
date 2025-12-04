```mermaid
flowchart TD

    %% AEGIS Speech to Text
    subgraph STT [Speech To Text Pipeline]
        A1[Audio Extraction - Video]
        A2[Speech To Text - Whisper / Azure]
        A3[Transcript Normalization - Cleanup]
    end

    %% AEGIS NLP
    subgraph NLP [NLP Processing Pipeline]
        A4[Sentence Splitting - Chunking]
        A5[Semantic Embedding Creation - Encoder]
    end

    %% AEGIS Storage
    subgraph STORAGE [Storage Layer]
        A6[Transcript Data Store - Text]
        A7[Vector Index Store - Embeddings]
    end

    %% AEGIS Search
    subgraph SEARCH [Search And Retrieval]
        Q1[User Query Input]
        Q2[Query Embedding Creation]
        Q3[Vector Similarity Search - Match]
        Q4[Ranked Segment Results]
        Q5[Jump To Video Timestamp]
    end

    A1 --> A2 --> A3 --> A4 --> A5
    A5 --> A6
    A5 --> A7

    Q1 --> Q2 --> Q3 --> Q4 --> Q5
```
