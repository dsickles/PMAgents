---
description: Simulates a debate between two conflicting personas to identify trade-offs.
---
# Simulate Roundtable

## Goal
Simulates a debate between two conflicting personas to identify trade-offs.

## Configuration
- **Inputs**: `Persona A` (e.g., CISO), `Persona B` (e.g., End User), `Topic`.
- **Context Needed**: `user_personas.md`.

## Steps
1.  **Load Personas**: Retrieve attributes for both characters.
2.  **Set Scene**: Define the conflict (e.g., "Discussing the new 2FA requirement").
3.  **Generate Dialogue**:
    -   Character A states their need.
    -   Character B pushes back based on their friction.
    -   Repeat for 3-4 turns.
4.  **Synthesize**: Identify the core trade-off.

## Output Template
```markdown
### ⚔️ Roundtable: [Topic]
**Participants**: Gary (CISO) vs. Linda (HR)

#### 💬 Transcript
**Gary**: "We need 2FA on every login. It's non-negotiable for compliance."
**Linda**: "Gary, my team logs in 20 times a day. If they have to use their phone every time, they will revolt."
**Gary**: "Security isn't convenient, Linda. It's necessary."
**Linda**: "Then make it remember the device for 24 hours. Otherwise, I'm buying a post-it note for every monitor."

#### ⚖️ Core Trade-off
**Security Compliance** vs. **Operational Efficiency**.
**Suggestion**: Implement "Remember this device for 30 days" to satisfy both.
```
