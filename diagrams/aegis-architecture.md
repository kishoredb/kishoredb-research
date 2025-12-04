# Aegis — NLP-Driven Video Intelligence Platform  
**Architecture Diagram**

This document describes the high-level architecture of the Aegis video intelligence system.  
The platform extracts insights from video using transcription, NLP pipelines, and  
metadata indexing to enable semantic search and content understanding.

---

## Architecture Diagram

```mermaid
flowchart LR
    U[User / Client App] --> UPLOAD[Video Upload API]
    UPLOAD --> STORE[Object Storage (Video)]
    STORE --> STT[Speech-to-Text Service]
    STT --> NLP[NLP Pipeline<br/> - Tokenization<br/> - Entity Extraction<br/> - Topic/Sentiment Detection]
    NLP --> METADATA[Metadata Store<br/>(Search Index)]
    U --> SEARCH[Search / Query API]
    SEARCH --> METADATA
    METADATA --> RESULTS[Search Results / Insights]
    RESULTS --> U
```
---

## Notes  
- The system separates **storage, transcription, and NLP analysis** for modularity.
- NLP results drive **semantic indexing** and **search insights**.


