---
description: Defines success metrics (HEART framework) and generates the corresponding technical instrumentation plan.
---
# Define Success Plan

## Goal
Defines success metrics (HEART framework) and generates the corresponding technical instrumentation plan.

## Configuration
- **Inputs**: `Feature Name`, `User Goal`.
- **Context Needed**: `product_strategy.md` (to align with company KPIs).

## Steps
1.  **Define Goal**: What is the user trying to do?
2.  **Map to HEART**:
    -   **H**appiness (NPS, CSAT)
    -   **E**ngagement (Sessions, Frequency)
    -   **A**doption (New user % usage)
    -   **R**etention (Churn, Return rate)
    -   **T**ask Success (Time to complete, Error rate)
3.  **Define Signals**: What user behaviors indicate these?
4.  **Define Metrics**: How do we calculate the signal?
5.  **Vanity Check (Devil's Advocate)**: Ask "Could this metric go up while the business actually gets worse?" (e.g., Time on Site increases because UI is confusing). If yes, define a Counter-Metric.

## Output Template
```markdown
### 📐 Success Plan: [Feature Name]

| Category | Goal | Signal | Metric |
| :--- | :--- | :--- | :--- |
| **Adoption** | Users find the new feature. | Clicks on "New" badge. | % of DAU who click entry point. |
| **Task Success** | Users complete the flow. | Reaching "Thank You" page. | Funnel Conversion Rate (Entry -> Success). |
| **Happiness** | Users value the output. | "Thumbs Up" on report. | CSAT Score > 4.0. |

#### 🔌 Instrumentation Requirements
*   [ ] Track Event: `feature_entry_click` (Props: `source`)
*   [ ] Track Event: `flow_complete` (Props: `time_taken_ms`)
```
