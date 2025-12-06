# SmartCare Diagram 5 — Deployment Flow

This diagram shows how SmartCare operates within assisted living environments,
from data collection to rule evaluation to caregiver notification.

---

```mermaid
flowchart TB

    subgraph INPUT [Data Collection Layer]
        A1[Observation Entry]
        A2[Vital Sign Device]
    end

    subgraph PROCESS [SmartCare.ProcessingService Module]
        B1[Data Capture]
        B2[Feature Extraction]
        B3[Rule Evaluation]
        B4[Severity Output]
    end

    subgraph OUTPUT [SmartCare.Notification Module]
        C1[Warning Signal]
        C2[Caregiver Alert]
    end

    A1 --> B1 --> B2 --> B3 --> B4 --> C1
    A2 --> B1
    C1 --> C2
