---
description: Evaluates the overall health of a strategic relationship based on engagement, sentiment, and roadmap alignment.
---
# Account Sentiment Pulse

## Goal
Evaluates the overall health of a strategic relationship based on engagement, sentiment, and roadmap alignment.

## Configuration
- **Inputs**: `Customer Name`.
- **Context Needed**: CRM notes (simulated), Support ticket volume, Roadmap alignment.

## Steps
1.  **Sentiment Analysis**: Check tone of last 3 emails/meetings (Positive/Neutral/Negative).
2.  **Support Pulse**: Are they filing "How to" tickets (Engagement) or "Bug" tickets (Frustration)?
3.  **Roadmap Match**: What % of their top 5 asks are on our next 2 quarters' roadmap?
4.  **Score**: Calculate `Health Score` (0-100).

## Output Template
```markdown
### ❤️ Account Sentiment Pulse: [Customer Name]
**Score**: 62/100 (⚠️ Warning)

| Dimension | Status | Notes |
| :--- | :--- | :--- |
| **Sentiment** | 🟡 Neutral | Last Checkin was "tense" due to downtime. |
| **Support** | 🔴 Critical | 5 active P1 bugs. Frustration high. |
| **Roadmap** | 🟢 Strong | We are building 4/5 of their top requests. |

**Prescription**:
1.  **Stabilize**: Engineering "Tiger Team" to kill the 5 P1 bugs.
2.  **Reassure**: PM + Eng Lead joint call to explain the roadmap wins coming.
```
