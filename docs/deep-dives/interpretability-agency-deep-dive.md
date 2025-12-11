<p align="center">
  <img src="https://raw.githubusercontent.com/kishoredb/kishoredb-research/main/assets/HumanAI.JPG" width="100" />
</p>

# 🔍 Deep Dive: Interpretability & Human Agency in AI-Mediated Work  
**Author:** Kishore D. B.  
**Updated:** 2025-12-08  
Location: `docs/deep-dives/interpretability-agency-deep-dive.md`

This deep dive covers my 2022–2023 research on how humans understand, question,
and exert agency when interacting with AI-generated explanations — especially in
high-stakes environments such as credit, fraud review, and compliance.

---

# 1. Problem Statement

AI explanation tools (e.g., SHAP, LIME, rule overrides) aim to increase trust.
But many explanations **fail** to help people reason about:

- why the model behaved this way  
- when it might be wrong  
- whether they should override  
- what uncertainty means  

The study explores:

**How do explanations influence user agency and their sense of control?**

---

# 2. Research Questions

1. What forms of explanation improve human understanding?  
2. How does explanation clarity affect override decisions?  
3. How does cognitive effort change when facing conflicting signals?  
4. How do domain experts vs novices interpret transparency cues?  

---

# 3. Study Design (Executed pre-2023)

### Methods
- Semi-structured interviews  
- Comparative explanation tests (“Which explanation is clearer?”)  
- Think-aloud reasoning of SHAP values  
- Cognitive load checklists  
- Perceived-agency ratings  

### Explanation types tested:
- SHAP bar summaries  
- SHAP waterfall sequences  
- rule-based “If X then Y” cards  
- natural-language summaries  

---

# 4. Findings (Conceptual + Observed Pre-Accident)

- Explanations increased **understanding**, but not always **agency**.  
- Too much detail made users feel overwhelmed → loss of perceived control.  
- Domain experience strongly shaped interpretation strategies.  
- Agency increased when explanations:  
  - acknowledged uncertainty  
  - presented alternative scenarios  
  - included “what would change the outcome” insights  

---

# 5. Connection to Systems in Repository

- **CredScore:** SHAP reasoning directly informed this study.  
- **Aegis:** Interpretability concepts influence ranking confidence displays.  
- **Fraud Engine:** Agency is tied to override handling.  
- **SmartCare:** Early-warning signals must preserve human judgment.  

---

# 6. Diagrams to Include

Will be placed in `diagrams/human-ai/`:

- `explanation-processing-model.md`  
- `human-ai-trust-cycle.md`

---

# 7. Reproducibility Notes

- [`Validation Notes`](../reproducibility/validation-notes.md)  
- [`Synthetic schema`](../reproducibility/datasets/sample-schema.md)

---

# 8. Cross-Links

### Related Deep Dives
- [`CredScore`](./credscore-deep-dive.md)  
- [`Metacognition`](./metacognition-deep-dive.md)

### Methodology
- [`Research Methodology`](../research-methodology.md)

### Human-Centered AI Hub
- [`Human-Centered AI`](../human-centered-ai.md)

---
