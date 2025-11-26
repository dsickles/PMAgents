---
description: Adopts a specific persona to critique a feature, copy, or design.
---
# Simulate Perspective

## Goal
Adopts a specific persona to critique a feature, copy, or design.

## Configuration
- **Inputs**: `Persona Name` (or "Random"), `Content to Review` (Feature spec, email draft, UI screenshot).
- **Context Needed**: `user_personas.md` (to load the character).

## Steps
1.  **Load Persona**: Read attributes from `user_personas.md`.
2.  **Analyze Content**: Look at the input through the lens of the persona's *Pain Points* and *Goals*.
3.  **React**:
    -   *Visceral Reaction*: First impression (Love/Hate/Confused).
    -   *Specific Critique*: Point out specific words or flows that work/fail.
4.  **Verdict**: Would they use it? (Yes/No).

## Output Template
```markdown
### 🎭 Simulation: [Persona Name]
**Verdict**: 👎 Pass

#### 💭 Inner Monologue
"Okay, I'm looking at this 'Advanced Filter' screen. Honestly? It scares me. There are too many dropdowns. I just want to see my team's vacation days."

#### 🛑 Friction Points
1.  **"Query Builder"**: I don't know what a query is. I'm in HR, not IT.
2.  **No Default View**: Why is the screen blank when I load it?

#### ✅ What I Liked
*   The 'Export to Excel' button is huge. I love that.
```
