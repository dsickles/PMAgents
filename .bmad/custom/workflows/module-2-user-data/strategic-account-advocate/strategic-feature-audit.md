---
description: Analyzes the status of delivered vs. open feature requests for specific strategic accounts.
---
# Strategic Feature Audit

## Goal
Analyzes the status of delivered vs. open feature requests for specific strategic accounts to demonstrate value or identify risks.

## Configuration
- **Inputs**: `Customer Name`, `Timeframe` (default: last 6 months).
- **Context Needed**: Access to `strategic_customers.md` (for account list) and Issue Tracker (simulated).

## Steps
1.  **Identify Commitments**: Scan the "Codex" or issue tracker for items tagged with the customer name.
2.  **Categorize Status**:
    -   ✅ **Delivered**: Shipped and closed.
    -   🚧 **In Progress**: Active dev, check ETA vs Promise Date.
    -   ⚠️ **At Risk**: No activity in 2 weeks or past due.
    -   🧊 **Icebox**: No movement.
3.  **Calculate "Trust Score"**: % of commitments met on time.
4.  **Generate Report**: A table tailored for a Checkin slide.

## Output Template
```markdown
### 🏛️ Strategic Audit: [Customer Name]
**Trust Score**: 85% (Healthy)

#### ✅ Delivered Value (Recent Wins)
*   **SSO Integration** (Shipped Oct 12) - *Enabled their EU expansion.*
*   **Custom Reporting** (Shipped Nov 01) - *Unblocked Finance team.*

#### ⚠️ At Risk (Action Required)
*   **Audit Logs API** (Due: Nov 15) - *Currently in QA, 3 days late.*
    *   **Recommendation**: Escalate to Engineering Lead [Name] today.

#### 🧊 Stalled Requests
*   **Dark Mode** - *No movement for 3 months.*
```
