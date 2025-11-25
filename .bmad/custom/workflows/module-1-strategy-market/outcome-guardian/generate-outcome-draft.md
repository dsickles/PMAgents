---
description: "Drafts new Strategic Outcomes and Metrics based on company strategy documents."
---

# Generate Strategic Outcome Draft

## Goal
Drafts new Strategic Outcomes and Metrics based on company strategy documents.

## Trigger
"Here is the CEO's annual letter. Draft Q1 Outcomes for the Mobile Team."

## Step Logic
1.  **Ingest Strategy**: Read the high-level strategy document.
2.  **Draft Outcomes**: Create qualitative, inspirational goals (The "Where").
3.  **Draft Success Metrics**: Create quantitative, time-bound metrics (The "How do we know").
4.  **Metric Quality Filter**: Check if Metric is an *Outcome* (Value) or *Output* (Volume). If Output, suggest a proxy Outcome.
5.  **Stress Test**: Apply the "SMART" filter (Specific, Measurable, Achievable, Relevant, Time-bound) to every Metric.

## Output
*   A Structured Outcome Table.
*   A "Measurement Plan" (How to track each Metric).
*   **Copy-Paste Considerations**:
    *   *Outcome Table*: Formatted for Gtmhub, Lattice, or a Google Sheet.
    *   *Measurement Plan*: Bulleted list for Data Science/Engineering tickets.
