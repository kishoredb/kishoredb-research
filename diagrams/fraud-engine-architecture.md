# Fraud Engine Architecture – AI Driven Fraud Detection  
Real Time Streaming, Graph And Hybrid AI (2023)

---

## Introduction

The Fraud Engine is an AI driven fraud detection system designed for **real time** transaction monitoring.  
It combines streaming data, machine learning models, and graph analytics to detect suspicious patterns early, while reducing false positives.

The platform is built around:

- Streaming pipelines using Kafka or Azure Event Hubs  
- A feature store for fast access to behavioural features  
- Multiple ML models for anomaly and sequence detection  
- Graph based analysis to detect complex fraud rings  
- Dashboards for monitoring and operations

This document describes the architecture using three diagrams:
1. Streaming And Feature Pipeline  
2. Model Fusion And Graph Based Detection  
3. Decision, Alerts And Monitoring

---

# Architecture Overview

The Fraud Engine follows a flow from **live events** to **real time decisions**:

1. **Streaming Ingestion**  
   Transactions and related events are ingested through Kafka or Azure Event Hubs.

2. **Feature Engineering And Feature Store**  
   Streams are enriched, features are computed, and stored in a fast feature store.

3. **Model Scoring And Graph Analysis**  
   Multiple models (LSTM, Autoencoders, Isolation Forest) generate risk signals, combined with graph based risk indicators from Neo4j.

4. **Hybrid Decision And Rules**  
   AI scores and rules are combined to produce final fraud risk flags.

5. **Monitoring And Feedback**  
   Power BI and Grafana dashboards show risk trends, model behaviour, and system health, feeding into continuous improvement.

This modular structure allows the engine to scale with higher volumes, new models, and evolving fraud patterns.

---

# Diagram A — Streaming And Feature Pipeline

This diagram shows how events enter the system and become enriched features for downstream models.  
Incoming transactions and events are ingested via Kafka or Azure Event Hubs, processed in a streaming layer, and written into a feature store such as Redis.  
The result is a low latency pipeline that keeps recent behavioural data ready for fraud detection models.

```mermaid
flowchart TB

    subgraph STREAM [FraudEngine.Streaming Module]
        F1[Incoming Events - Transactions]
        F2[Kafka Or Azure Event Hubs]
        F3[Stream Processing And Enrichment]
    end

    subgraph FEATURE [Feature Store]
        F4[Derived Features - Behaviour Profiles]
        F5[Feature Storage - Redis]
    end

    F1 --> F2 --> F3 --> F4 --> F5
```

---

# Diagram B — Model Fusion And Graph Based Detection

This diagram shows how the Fraud Engine uses multiple models and graph analytics to detect fraud patterns.  
The feature store feeds different model types: sequence models for temporal patterns, anomaly models for unusual behaviour, and tree based models for structured signals.  
In parallel, a graph database such as Neo4j is used to model relationships between entities and surface complex fraud rings.

```mermaid
flowchart TB

    subgraph FEATURE [Feature Store]
        F5[Feature Storage - Redis]
    end

    subgraph MODELS [FraudEngine.Models Module]
        M1[LSTM Sequence Model]
        M2[Autoencoder Anomaly Model]
        M3[Isolation Forest Model]
        M4[Combine Model Risk Signals]
    end

    subgraph GRAPH [Graph Analysis Module]
        G1[Neo4j GraphDB]
        G2[Graph Features - Links And Communities]
        G3[Graph Risk Signals]
    end

    subgraph OUTPUT [Aggregated Risk Signals]
        O1[Combined Model Score]
        O2[Graph Based Risk Score]
        O3[Overall Fraud Risk Indicator]
    end

    F5 --> M1
    F5 --> M2
    F5 --> M3

    F5 --> G1
    G1 --> G2 --> G3

    M1 --> M4
    M2 --> M4
    M3 --> M4

    M4 --> O1
    G3 --> O2

    O1 --> O3
    O2 --> O3
```

---

# Diagram C — Decision, Alerts And Monitoring

This diagram shows how risk signals from models and graph analysis are turned into actions and monitored over time.  
A hybrid decision layer combines AI scores with rules, producing fraud flags and recommended actions such as approve, review, or block.  
Dashboards in Power BI and Grafana show trends, alert volumes, and system metrics, supporting both operations and continuous improvement.

```mermaid
flowchart TB

    subgraph RISK_INPUT [Risk Signals]
        O3[Overall Fraud Risk Indicator]
    end

    subgraph DECISION [Decision And Rules Module]
        D1[Hybrid Rules And AI Engine]
        D2[Fraud Risk Score And Flags]
        D3[Route To Actions - Approve Review Block]
    end

    subgraph MONITOR [Monitoring And Dashboards]
        MON1[Power BI Fraud Dashboards]
        MON2[Grafana Pipeline Metrics]
        MON3[Model And System Health Views]
    end

    subgraph FEEDBACK [Feedback And Tuning]
        FB1[Analyst Feedback On Alerts]
        FB2[Update Rules And Thresholds]
        FB3[Feed Back Into Model Improvement]
    end

    RISK_INPUT --> D1 --> D2 --> D3

    D2 --> MON1
    D2 --> MON2
    D2 --> MON3

    D3 --> FB1 --> FB2 --> FB3
```

---

## Business Impact

The Fraud Engine was designed to reduce losses while keeping alert quality high:

- Around **40 percent reduction in fraud losses**  
- Around **20 percent faster fraud detection time** through real time scoring  
- Reduction of false positives using **hybrid rules and AI models**, improving analyst productivity  

---

## Summary

The Fraud Engine is a real time, AI driven fraud detection platform that combines streaming, feature stores, multiple ML models, and graph analysis.  
Its modular design allows each part of the system like streaming, features, models, graph analytics, decision logic, and dashboards to evolve as fraud patterns and technologies change.

By providing both powerful detection capabilities and operational visibility, it supports proactive fraud management in modern, high volume environments.

---

## 📘 Fraud Engine Diagram Suite

- 🔹 **End-to-End Overview**  
  [`fraud-engine-overview.md`](./fraud-engine/fraud-engine-overview.md)

- 🔹 **Feature Extraction Flow**  
  [`fraud-engine-feature-flow.md`](./fraud-engine/fraud-engine-feature-flow.md)

- 🔹 **Detection Pipeline**  
  [`fraud-engine-detection-pipeline.md`](./fraud-engine/fraud-engine-detection-pipeline.md)

- 🔹 **Evaluation Pipeline**  
  [`fraud-engine-evaluation.md`](./fraud-engine/fraud-engine-evaluation.md)

- 🔹 **Deployment Architecture**  
  [`fraud-engine-deployment.md`](./fraud-engine/fraud-engine-deployment.md)


