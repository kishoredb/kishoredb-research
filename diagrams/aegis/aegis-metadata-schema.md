# AEGIS Diagram 2 — Metadata & Storage Schema

This diagram explains how AEGIS structures its internal data: transcripts, embeddings, 
timestamps, and metadata. It shows how segments are stored, how embeddings relate to the 
transcript chunks, and how video-level metadata is organized for efficient retrieval.

This provides reviewers with a clear understanding of AEGIS’s information model — a key 
research element for reproducibility and system design clarity.

---

```mermaid
classDiagram

    class Video {
        +video_id
        +title
        +duration
        +file_path
    }

    class TranscriptChunk {
        +chunk_id
        +video_id
        +start_time
        +end_time
        +text
    }

    class Embedding {
        +embedding_id
        +chunk_id
        +vector[768]
    }

    class Metadata {
        +video_id
        +topics[]
        +tags[]
        +speakers[]
    }

    Video --> TranscriptChunk : "has many"
    TranscriptChunk --> Embedding : "has one"
    Video --> Metadata : "has one"
