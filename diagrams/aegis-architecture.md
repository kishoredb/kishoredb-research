```mermaid
flowchart TD
    A1[Extract Audio]
    A2[Transcribe (Whisper/Azure STT)]
    A3[Clean & Segment Text]
    A4[Chunk + Timestamps]
    A5[Embed (BERT/GPT)]
    A6[Store Transcript]
    A7[Store Vectors]

    A1 --> A2 --> A3 --> A4 --> A5
    A5 --> A6
    A5 --> A7
```
