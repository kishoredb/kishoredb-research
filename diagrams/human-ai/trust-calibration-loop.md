# Trust Calibration Loop

This diagram models how humans regulate trust when interacting with AI systems.

It shows the feedback cycle between:

AI output → human interpretation → confidence calibration → decision → outcome → updated trust.


```mermaid
flowchart TB

    A[AI Output] --> B[Human Interprets Explanation]
    B --> C[Confidence Assessment]
    C --> D[Decision or Override]
    D --> E[Outcome Observed]
    E --> F[Trust Adjustment]
    F --> B

