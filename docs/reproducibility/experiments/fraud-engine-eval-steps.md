# Fraud Engine — Evaluation Steps (Synthetic Demo)

This document provides a simplified evaluation flow for the Fraud Engine using
synthetic time-series transaction data.

---

## 1. Synthetic Dataset Structure

| txn_id | amount | merchant | hour | desc_text | label |
|-------|--------|----------|------|-----------|-------|
| 1     | 220.5  | food     | 14   | "tap payment" | legit |
| 2     | 1880.0 | jewelry  | 03   | "manual entry" | fraud |

---

## 2. Signal Extraction

- behaviour patterns  
- recurrence timing  
- NLP keyword flags  
- rule-based risk tags  

---

## 3. Detector-Level Evaluation

Each detector is evaluated separately:

- time-series anomaly detector → anomaly score distribution  
- NLP feature detector → keyword recall  
- hybrid risk scorer → precision/recall  

---

## 4. Score Fusion Evaluation

After combining detectors:

Metrics:

- Precision@K  
- Recall@K  
- False positive rate  
- Case resolution rate (synthetic)  

---

## 5. Human Review Simulation

Synthetic “analyst validation labels” to mimic fraud team judgement.  

Used to check:

- explainability clarity  
- ranking consistency  
- review workload impact  
