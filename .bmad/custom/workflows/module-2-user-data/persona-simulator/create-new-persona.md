---
description: Generates a detailed, reusable persona profile based on raw demographics, job descriptions, or interview notes.
---
# Create New Persona

## Goal
Generates a detailed, reusable persona profile based on raw demographics, job descriptions, or interview notes.

## Configuration
- **Inputs**: `Role Title`, `Grounding Data` (Required: Interview notes, LinkedIn profile, Job description, or raw feedback).
- **Context Needed**: `user_personas.md` (to save the output).

## Steps
1.  **Analyze Grounding Data**: Extract real quotes, frustrations, and goals from the input.
2.  **Define Base Attributes**: Name, Age, Job Title, Tech Savviness (1-10).
3.  **Define Psychographics**: What keeps them up at night? What is their primary motivation?
4.  **Define "Trigger Phrases"**: What words make them angry? What words make them buy?
5.  **Generate Profile**: Create a markdown card for `user_personas.md`.

## Output Template
```markdown
### 👤 Persona: [Name] - [Role]
**"Quote that summarizes their worldview."**

| Attribute | Value |
| :--- | :--- |
| **Tech Savviness** | 🟢 High (8/10) |
| **Risk Tolerance** | 🔴 Low (Avoids new tools) |
| **Key Goal** | "Don't get hacked." |

#### 🧠 Mindset
*   **Loves**: Audit logs, SSO, "Enterprise-Grade".
*   **Hates**: "Beta" features, undefined permissions, cute UI.

#### 💬 Voice
Formal, skeptical, asks about compliance first.
```
