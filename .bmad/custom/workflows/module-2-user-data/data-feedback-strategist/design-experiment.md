---
description: Designs A/B tests, rollout strategies, and validation criteria to prove a hypothesis.
---
# Design Experiment

## Goal
Designs A/B tests, rollout strategies, and validation criteria to prove a hypothesis.

## Configuration
- **Inputs**: `Hypothesis`, `Risk Level`.
- **Context Needed**: `technical_constraints.md` (for rollout capabilities).

## Steps
1.  **Refine Hypothesis**: "If we do X, then Y will happen, because Z."
2.  **ROI of Learning Check**: Ask "What is the cost of being wrong?"
    *   *Low Cost*: Recommend "Just Ship It" (Monitor in prod).
    *   *High Cost*: Proceed to Experiment Design.
3.  **Determine Method**: A/B Test? Painted Door? Phased Rollout?
4.  **Calculate Sample Size**: (Simulated estimation based on risk).
5.  **Define Success/Fail Criteria**: When do we stop the test?

## Output Template
```markdown
### 🧪 Experiment Design: [Name]
**Hypothesis**: Adding social proof to the checkout page will increase conversion by 5%.

#### Parameters
*   **Method**: A/B Test (50/50 split).
*   **Duration**: 2 weeks (minimum).
*   **Target Audience**: New visitors only.

#### Success Criteria
*   **Win**: Conversion Rate > 2.5% (Baseline: 2.0%).
*   **Kill Switch**: Support tickets > 10/day or Latency > 200ms.

#### Variants
*   **Control**: Current checkout page.
*   **Variant A**: Checkout page with "50 people bought this" banner.
```
