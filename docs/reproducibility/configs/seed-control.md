# Seed Control for Reproducibility

To ensure deterministic behaviour during conceptual demonstrations:

```python
import numpy as np
import random

np.random.seed(42)
random.seed(42)
