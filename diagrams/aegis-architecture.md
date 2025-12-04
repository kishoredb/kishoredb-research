```mermaid
flowchart TD

    subgraph STT
        direction TB
        AEGIS_STT_Title[AEGIS.STT - Speech-to-Text]
        A1[Extract Audio (FFmpeg)]
        A2[Transcribe Audio (Whisper / Azure STT)]
        A3[Raw Transcript]
    end

    subgraph NLP
        direction TB
        NLP_Title[AEGIS.NLP - Embeddings and Semantic Processing]
        N1[Text Cleanup and Sentence Splitting]
        N2[Chunking with Timestamps]
        N3[Embedding Generation (BERT / GPT)]
    end

    subgraph INDEX
        direction TB
        INDEX_Title[AEGIS.Index - Storage and Search]
        I1[CosmosDB (Transcript and Metadata)]
        I2[Azure Cognitive Search (Vector Index)]
    end

    subgraph QUERY
        direction TB
        QUERY_Title[AEGIS.Search - Query and Ranking]
        Q1[User Query]
        Q2[Query Embedding]
        Q3[Semantic Similarity Ranking]
    end

    subgraph PLAYER
        direction TB
        PLAYER_Title[AEGIS.Player - Video Navigation]
        P1[Matched Timestamps]
        P2[Jump to Video Frame]
    end

    subgraph EXT
        direction TB
        EXT_Title[External Interfaces]
        U1[Upload UI]
        U2[Search UI]
        U3[Video Player]
    end

    U1 --> A1
    A1 --> A2
    A2 --> A3

    A3 --> N1
    N1 --> N2
    N2 --> N3

    N2 --> I1
    N3 --> I2

    U2 --> Q1
    Q1 --> Q2
    Q2 --> Q3

    Q3 --> P1
    P1 --> P2
    P2 --> U3
```
