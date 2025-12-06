# Fraud Engine Diagram 3 — Modeling Pipeline

This diagram shows how anomaly detection models and rule engines
generate individual scores which are then fused into a final risk output.

---

```mermaid
flowchart TB

    subgraph INPUT [FraudEngine.TrainingInput Module]
        A1[Feature Vector]
        A2[Historical Labels]
    end

    subgraph MODELS [FraudEngine.ModelTraining Module]
        B1[Anomaly Detector Training]
        B2[Supervised Model Training]
        B3[Rule Engine Calibration]
    end

    subgraph SCORES [FraudEngine.ModelScores Module]
        C1[Anomaly Score]
        C2[Supervised Score]
        C3[Rule Based Score]
        C4[Score Fusion]
    end

    subgraph OUTPUT [FraudEngine.ScoreOutput Module]
        D1[Final Risk Score]
    end

    A1 --> B1 --> C1 --> C4 --> D1
    A1 --> B2 --> C2 --> C4
    A1 --> B3 --> C3 --> C4
    A2 --> B2
