---
description: "Create a unified 'Master Portfolio View' from disparate team updates."
---

# Roadmap Sync

## Goal
Create a unified "Master Portfolio View" from disparate team updates.

## Trigger
"Here are the updates from Team A, Team B, and Team C. What does the Q3 roadmap look like?"

## Step Logic
1.  **Ingest & Interrogate**: Read updates. If data is unstructured/messy, stop and ask: *"I need the Start Date, End Date, and Dependencies for [Project X]. Please provide them."*
2.  **Normalize**: Map all items to a standard timeline (Now, Next, Later or Q1/Q2/Q3).
3.  **Link**: Identify cross-team dependencies (e.g., "Team A needs API from Team B").
4.  **Visualize**: Generate a Mermaid Gantt chart.
    *   *Complexity Check*: If >15 items, automatically group by "Theme" or "Epic" to maintain readability, or offer to generate per-team charts.

## Output
*   A Mermaid Gantt Chart of the Master Roadmap.
*   A "Dependency Risk Log" highlighting unaligned dates.
*   **Copy-Paste Considerations**:
    *   *Mermaid Chart*: Ready for Jira/Confluence/Notion (using code block).
    *   *Risk Log*: Formatted as a bulleted list for immediate email/Slack distribution.
