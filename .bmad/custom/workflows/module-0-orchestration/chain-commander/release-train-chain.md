---
description: Orchestrates the flow from Spec -> Cleanup -> Comms -> Notification.
---
# Release Train Chain

## Goal
To safely ship a release and ensure everyone knows about it.

## Steps
1.  **Spec**: Call `Agile Captain`. Generate `Release Scope`.
2.  **Cleanup**: Call `Bugs Steward`. Verify `Tech Debt` ratio.
3.  **Gate**: **[STOP]** Ask for Go/No-Go decision.
4.  **Comms**: Call `Release Communicator`. Generate `Release Notes`.
5.  **Notify**: Call `Stakeholder Liaison`. Draft `Slack Announcement`.

## Output (State Tracking)
- **Status**: `IN_PROGRESS` | `BLOCKED` | `DONE`
- **Current Step**: [Step Name]
- **Artifacts**: [Link to Release Notes], [Link to Announcement]

## Audition
"Release v2.4 is **READY**. Tech Debt ratio is 15% (Pass). Release Notes generated. Shall I send the announcement draft to your drafts folder?"
