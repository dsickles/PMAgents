---
description: Generates structured summaries from raw notes.
---
# Meeting Minutes Synthesizer

## Goal
To turn raw transcript/notes into a clear record of decisions and actions.

## Steps
1.  **Ingest**: Read raw transcript/notes.
2.  **Extract**: Identify `Decisions`, `Action Items` (Who/What/When), and `Open Questions`.
3.  **Format**: Structure into a standard "Minutes" block.

## Output (Email/Confluence Block)
```markdown
**Meeting Summary: [Topic]**
✅ **Decisions**:
*   [Decision 1]
👉 **Action Items**:
*   @[Person]: [Task] by [Date].
```

## Audition
```markdown
**Meeting Summary: Q3 Planning**
✅ **Decisions**:
*   Greenlit 'Project X'.
👉 **Action Items**:
*   @Sarah: Draft PRD by Friday.
*   @Mike: Update Jira board.
```
