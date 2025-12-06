# AEGIS Diagram 3 — Query Processing & Ranking Flow

This diagram illustrates how a natural-language user query is converted into a semantic 
representation, matched against AEGIS’ vector index, ranked, and mapped back to video 
timestamps for playback.

It provides a research-oriented view of the internal decision-making stages within the 
search pipeline.

---

```mermaid
flowchart TB

    subgraph QUERY [1. Query Processing]
        direction TB
        A[User Query]
        B[Query Embedding Creation]
        A --> B
    end

    subgraph MATCH [2. Vector Similarity Search]
        direction TB
        C[Top-K Nearest Segments]
        B --> C
    end

    subgraph RANK [3. Re-Ranking & Scoring]
        direction TB
        D1[Semantic Score]
        D2[Context Score]
        D3[Timestamp Proximity Score]
        E[Final Ranked Results]

        C --> D1 --> E
        C --> D2 --> E
        C --> D3 --> E
    end

    subgraph OUTPUT [4. Playback Mapping]
        direction TB
        F[Timestamp Retrieval]
        G[Video Player Jump-to-Time]
        E --> F --> G
    end
