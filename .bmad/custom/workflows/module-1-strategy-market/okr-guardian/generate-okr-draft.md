---
description: "Drafts new Objectives and Key Results (OKRs) based on company strategy documents."
---

# Generate OKR Draft

## Goal
Drafts new Objectives and Key Results (OKRs) based on company strategy documents.

## Trigger
"Here is the CEO's annual letter. Draft Q1 OKRs for the Mobile Team."

## Step Logic
1.  **Ingest Strategy**: Read the high-level strategy document.
2.  **Draft Objectives**: Create qualitative, inspirational goals (The "Where").
3.  **Draft Key Results**: Create quantitative, time-bound metrics (The "How do we know").
4.  **Metric Quality Filter**: Check if KR is an *Outcome* (Value) or *Output* (Volume). If Output, suggest a proxy Outcome.
5.  **Stress Test**: Apply the "SMART" filter (Specific, Measurable, Achievable, Relevant, Time-bound) to every KR.

## Output
*   A Structured OKR Table.
*   A "Measurement Plan" (How to track each KR).
*   **Copy-Paste Considerations**:
    *   *OKR Table*: Formatted for Gtmhub, Lattice, or a Google Sheet.
    *   *Measurement Plan*: Bulleted list for Data Science/Engineering tickets.
