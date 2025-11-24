---
description: "Objectively rank features to resolve 'everything is P0' conflicts."
---

# Prioritization Matrix

## Goal
Objectively rank features to resolve "everything is P0" conflicts.

## Trigger
"We have 20 features requested for the next sprint but capacity for 5."

## Step Logic
1.  **Scoring Framework Selection**: Ask user to choose RICE, WSJF (Weighted Shortest Job First), or Value/Effort.
2.  **Scoring & Calibration**: Interview user for inputs.
    *   *Confidence Check*: If user says "Confidence = 100%" (High), ask: *"Do you have engineering estimates and user research? If not, I recommend lowering Confidence to 80%."*
3.  **Ranking**: Calculate scores and sort.
4.  **Cutline**: Draw the line based on available capacity.

## Output
*   A Ranked Backlog Table.
*   A "Cutline Report" showing what didn't make it and why.
*   **Copy-Paste Considerations**:
    *   *Ranked Backlog*: CSV-compatible format for easy import into Jira/Excel.
    *   *Cutline Report*: Empathetic but firm text block for stakeholder communication.
