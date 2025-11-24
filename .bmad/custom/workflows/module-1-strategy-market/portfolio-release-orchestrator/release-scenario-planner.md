---
description: "Model trade-offs to help stakeholders make hard decisions."
---

# Release Scenario Planner

## Goal
Model trade-offs to help stakeholders make hard decisions.

## Trigger
"We need to launch Feature X by Date Y, but we're behind. What are our options?"

## Step Logic
1.  **Baseline**: Establish the current trajectory (The "Do Nothing" scenario).
2.  **Constraint Identification**: Ask *"Is the target date driven by market coordination (hard constraint) or executive desire (soft constraint)?"* to tailor the analysis.
3.  **Variable Adjustment**: Model 3 scenarios:
    *   *Fixed Date*: What scope must be cut to hit the date?
    *   *Fixed Scope*: When will it actually land if we keep all features?
    *   *Resource Shift*: What if we move devs from Project B to Project A?
4.  **Impact Analysis**: Highlight the cost of each option (e.g., "Delaying Project B risks Q4 churn").

## Output
*   A "Scenario Comparison Table" (Markdown).
*   A Recommendation based on RICE/Value maximization.
*   **Copy-Paste Considerations**:
    *   *Comparison Table*: Markdown table ready for slide decks or decision docs.
    *   *Recommendation*: Concise "Executive Summary" block for top of email.
