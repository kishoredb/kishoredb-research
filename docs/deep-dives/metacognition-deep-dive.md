<p align="center">
  <img src="https://raw.githubusercontent.com/kishoredb/kishoredb-research/main/assets/HumanAI.JPG" width="100" />
</p>

# 🧠 Deep Dive: Metacognitive Strategies in AI-Assisted Decision-Making  
**Author:** Kishore D. B.  
**Updated:** 2025-12-08  
Location: `docs/deep-dives/metacognition-deep-dive.md`

This deep dive expands the research work initiated in early 2023 on how humans
monitor, regulate, and adjust their decisions when interacting with AI systems.
The work combines conceptual design (pre-May 2023) with post-2023 recovery-phase
analysis and modelling.

---

# 1. Problem Statement

AI systems are increasingly present in decisions involving credit, fraud,
healthcare, and compliance. Yet humans do not simply “follow” or “ignore” AI
suggestions — they:

- check their confidence  
- evaluate mismatch between expectation and AI output  
- adjust behaviour as uncertainty changes  
- sometimes override AI even when AI is right  

The core question behind this study was:

**How do humans use metacognitive processes (monitoring, calibration,
self-regulation) when interacting with AI assistance?**

---

# 2. Research Questions

1. How do humans calibrate confidence before and after seeing an AI suggestion?  
2. What triggers an override, agreement, or hesitation?  
3. How does uncertainty visualization influence trust?  
4. Are different cognitive profiles affected differently by AI cues?  

---

# 3. Study Design (Pre-Accident + Conceptual Post-Accident)

### Methods designed & partially executed in early 2023:
- Think-aloud interviews  
- Confidence rating scales  
- Task-based decision simulations  
- Behavioural logging of:  
  - pre-AI vs post-AI confidence  
  - time taken to override  
  - hesitations and backtracking  

### Conceptual analysis performed during 2023–24 recovery:
- Metacognitive loop modelling  
- New calibration frameworks  
- Integration with explainability research  

---

# 4. Participants & Data Sources

- Early study participants:  
  - credit analysts  
  - fraud reviewers  
  - compliance professionals  

- Synthetic tasks used:  
  - credit risk vignettes  
  - fraud anomaly scenarios  
  - ambiguous reasoning tasks  

---

# 5. Key Findings (Conceptual)

- Humans rely on **pattern familiarity**, even when AI is more accurate.  
- Confidence often drops **after** seeing an AI suggestion — even when correct.  
- **Uncertainty displays** (confidence intervals, SHAP visuals) helped reduce rash overrides.  
- Cognitive strategies varied:  
  - fast pattern matchers  
  - reflective calibrators  
  - rule-first decision makers  

---

# 6. How This Connects to Systems in This Repository

Metacognitive concepts inform:

- **Aegis:** how users interpret retrieval confidence  
- **CredScore:** how analysts interpret SHAP outputs  
- **Fraud Engine:** how reviewers rely on anomaly scores  
- **SmartCare:** how caregivers interpret early-warning signals  

---

# 7. Diagrams To Include

These diagrams will be generated in the HAI diagram suite:

- `metacognitive-loop.md`  
- `human-ai-trust-cycle.md`  
- `explanation-processing-model.md`  

---

# 8. Reproducibility Notes

Relevant reproducibility materials:

- [`Synthetic dataset schema`](../reproducibility/datasets/sample-schema.md)  
- [`Validation notes`](../reproducibility/validation-notes.md)  
- [`Reproducibility guidelines`](../reproducibility/environment/reproducibility-guidelines.md)

---

# 9. Cross-Links

### Related Deep Dives
- [`CredScore`](./credscore-deep-dive.md)  
- [`Aegis`](./aegis-deep-dive.md)

### Related Methodology
- [`Research Methodology`](../research-methodology.md)

### Human-Centered AI Home
- [`Human-Centered AI`](../human-centered-ai.md)

---

# 10. Related Human–AI Cognitive Diagrams

- **Trust Calibration Loop**  
  [`trust-calibration-loop.md`](../../diagrams/human-ai/trust-calibration-loop.md)

- **Cognitive Load Flow**  
  [`cognitive-load-flow.md`](../../diagrams/human-ai/cognitive-load-flow.md)

- **Explanation Misalignment Flow**  
  [`explanation-misalignment-flow.md`](../../diagrams/human-ai/explanation-misalignment-flow.md)

---

