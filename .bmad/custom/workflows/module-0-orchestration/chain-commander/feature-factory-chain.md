---
description: Orchestrates the flow from Opportunity -> Validation -> Definition -> Feasibility.
---
# Feature Factory Chain

## Goal
To take a raw idea and turn it into an engineering-ready spec.

## Steps
1.  **Opportunity**: Call `Market Sentinel`. Wait for `Gap Analysis`.
2.  **Validation**: Call `Strategic Advocate`. Check `Gap Analysis` against `Key Accounts`.
3.  **Definition**: Call `Requirement Architect`. Generate `PRD Draft`.
4.  **Gate**: **[STOP]** Ask user for PRD Approval.
5.  **Feasibility**: Call `Technical Partner`. Generate `Feasibility Report`.

## Output (State Tracking)
- **Status**: `IN_PROGRESS` | `BLOCKED` | `DONE`
- **Current Step**: [Step Name]
- **Artifacts**: [Link to PRD], [Link to Feasibility Report]

## Audition
"Chain 'Feature-123' Status: **BLOCKED**. Step 3 (Definition) complete. Waiting for User Approval on PRD before proceeding to Feasibility."
