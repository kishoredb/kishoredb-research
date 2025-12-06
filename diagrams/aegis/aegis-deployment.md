# AEGIS Diagram 5 – Deployment Architecture

This diagram shows how AEGIS is deployed in a cloud-native environment.  
It highlights the separation of ingestion, processing, indexing, and search services.  
The structure matches the format used in the other AEGIS diagrams.

---

```mermaid
flowchart TB

    subgraph CLIENT [Client Layer]
        C1[User Interface]
        C2[Query API Client]
    end

    subgraph API [API Gateway Layer]
        A1[REST API Gateway]
        A2[Auth And Access Control]
    end

    subgraph INGEST [AEGIS.Ingest Service]
        I1[Video Upload Endpoint]
        I2[Video Storage In Blob]
    end

    subgraph PROCESS [AEGIS.Processing Service]
        P1[Audio Extraction]
        P2[Speech To Text]
        P3[Transcript Cleanup]
        P4[Chunking And Embedding]
    end

    subgraph STORAGE [Data Storage Layer]
        S1[Transcript Storage]
        S2[Vector Index Storage]
    end

    subgraph SEARCH [AEGIS.Search Service]
        Q1[Query Embedding]
        Q2[Vector Similarity Search]
        Q3[Ranked Results]
    end

    C1 --> C2
    C2 --> A1 --> A2

    A1 --> I1 --> I2
    I2 --> P1 --> P2 --> P3 --> P4

    P3 --> S1
    P4 --> S2

    C2 --> Q1 --> Q2 --> Q3
    S2 --> Q2
    S1 --> Q3
