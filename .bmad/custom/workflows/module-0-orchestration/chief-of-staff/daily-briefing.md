---
description: Reviews all active workflows and project states to suggest prioritized actions.
---
# Daily Briefing

## Goal
To provide a prioritized "Morning Brief" of what needs the PM's attention.

## Steps
1.  **Scan**: Check the status of all active chains (via Workflow Orchestrator).
2.  **Prioritize**: Sort items by `Blocked` > `Pending Approval` > `In Progress`.
3.  **Format**: Generate a "Morning Brief" block using the template below.

## Output Template (Slack Block)
```markdown
☀️ **Morning Briefing**
🔴 **Blocked**: [Workflow Name] (Waiting on [Agent/Person])
🟡 **Needs Approval**: [Workflow Name] (Ready for Go/No-Go)
🟢 **In Progress**: [Workflow Name]
```

## Audition
```markdown
☀️ **Morning Briefing**
🔴 **Blocked**: Feature Factory (Waiting on *Strategic Advocate*)
🟡 **Needs Approval**: Release Train v2.1 (Ready for *Go/No-Go*)
🟢 **In Progress**: Q3 Strategy Refresh
```
