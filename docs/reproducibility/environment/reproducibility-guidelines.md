# Reproducibility Guidelines

This document summarizes the practices used to ensure reproducible results across experiments.

## 1. Deterministic Execution
- Fix random seeds for NumPy, Python, Torch.
- Log seed values in experiment metadata.

## 2. Version Everything
- Dataset versions
- Model versions
- Config versions

## 3. Log All Experiments
At minimum:
- Input parameters  
- Model hyperparameters  
- Evaluation metrics  
- Notes from human reviewers

## 4. Use Stable Validation Sets
Synthetic datasets in this folder support conceptual demonstration of reproducibility without real data.
