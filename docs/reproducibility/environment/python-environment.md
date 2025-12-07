# Python / Conda Environment Notes

These notes provide a reproducible environment baseline used in experiments.

## 🐍 Recommended Python Version
Python 3.10 or 3.11


## 📦 Example Dependency Set (Minimal)

numpy
pandas
scikit-learn
xgboost
matplotlib
transformers
torch


## 🔐 Reproducibility Recommendations
- Use `pip-compile` or `conda env export` for locking.
- Document environment hashes (`sha256`) after export.
- Pin versions for ML libraries to avoid nondeterministic updates.

