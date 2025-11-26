# Enterprise PM Agent Suite 🚀

**Current Status**: Phase 1 Complete (Foundation & Strategy)
**Version**: 0.1.0

## 🎯 Mission
To empower Enterprise Product Managers by acting as a comprehensive force multiplier. Beyond automating the "busy work"—scheduling, ticket writing, status updates—this suite provides deep **thought partnership** across the entire product lifecycle. From **Strategy** and **Prioritization** to **Stakeholder Management** and **Execution**, we enable PMs to drive impact with **Empathy** and **Innovation**.

## 🏗️ Architecture: The 7-Module System
We are building a suite of **24 Specialized Agents** organized into 7 logical modules.

| Module | Focus | Status | Agents |
| :--- | :--- | :--- | :--- |
| **0. Orchestration** | Routing & Utilities | ✅ **Live** | `Chief of Staff`, `PM Toolkit`, `Session Facilitator`, `Chain Commander` |
| **1. Strategy & Market** | The "Why" & "When" | ✅ **Live** | `Market Sentinel`, `Portfolio Orchestrator`, `Outcome Guardian` |
| **2. User & Data** | The "Who" & "What" | 🚧 *Next* | *Planned* |
| **3. Definition** | Requirements | ⏳ *Pending* | *Planned* |
| **4. Execution** | Engineering | ⏳ *Pending* | *Planned* |
| **5. Go-to-Market** | Launch | ⏳ *Pending* | *Planned* |
| **6. Leadership** | Team Health | ⏳ *Pending* | *Planned* |

## 🧠 The Codex (Shared Context)
The "Brain" of the suite. All agents read from these files to ensure alignment.
*   ✅ **Populated with**: Workday Student (Academic Advising) context.
*   **Files**: `company_mission.md`, `product_strategy.md`, `user_personas.md`, `technical_constraints.md`, `brand_voice.md`, `stakeholder_map.md`.

## 🤖 Live Agents & Workflows

### Module 0: Orchestration
*   **Chief of Staff**: The intelligent interface. Routes requests, clarifies intent, and manages the context.
    *   `route-request`: Analyzes user input, determines intent, and dispatches to the correct specialist agent.
    *   `codex-bootstrapper`: A guided interview process to populate the 6 core Codex files from scratch.
    *   `daily-briefing`: Scans calendars, Jira, and Slack to generate a "Morning Briefing" for the PM.
    *   `update-codex`: Controlled workflow to modify the shared context.
*   **PM Toolkit**: Universal utilities for daily tasks.
    *   `meeting-minutes-synthesizer`: Ingests raw transcripts and outputs structured minutes with decisions and action items.
    *   `decision-framework-selector`: Recommends the best decision-making model (RACI, DACI, SPADE) for a problem.
    *   `document-quality-audit`: Scores a PRD or Spec against a "Quality Rubric" (Clarity, Completeness, Feasibility).
*   **Session Facilitator**: Orchestrates collaboration between specialized agents to generate unified workshop deliverables, ensuring all perspectives are integrated into final decisions.
    *   `roadmap-planning`: Facilitates a session to prioritize features and define the roadmap.
    *   `release-planning`: Guides the team through scope negotiation and release commitment.
    *   `design-engineering-handoff`: Structured protocol for handing off designs to engineering, ensuring no details are lost.
*   **Chain Commander**: Manages complex, multi-agent chains.
    *   `strategy-refresh-chain`: Orchestrates the flow from Market Sentinel -> Portfolio Orchestrator -> Outcome Guardian to update strategy.
    *   `feature-factory-chain`: Orchestrates the flow from Idea -> PRD -> Engineering Ticket.
    *   `release-train-chain`: Orchestrates the release process from Code Freeze to Launch.

### Module 1: Strategy & Market
*   **Market Sentinel**: The competitive intelligence analyst. Monitors the landscape and identifies threats.
    *   `competitor-capability-comparison`: Generates detailed "Win/Lose/Tie" matrices comparing specific features against competitors.
    *   `win-loss-pattern-analysis`: Analyzes CRM data to identify systemic reasons for winning or losing deals.
    *   `market-opportunity-scanner`: Scans industry trends and news to identify emerging opportunities or threats.
    *   `b2b-pmf-health-check`: Assesses Product-Market Fit signals specifically for B2B contexts (churn, NRR, sales cycle).
*   **Portfolio Orchestrator**: The "Air Traffic Controller" for roadmaps and releases.
    *   `roadmap-sync`: Merges disparate team updates into a master Gantt chart, flagging dependencies.
    *   `release-scenario-planner`: Models "Fixed Date" vs. "Fixed Scope" trade-offs for leadership.
    *   `prioritization-matrix`: Scores features using RICE, WSJF, or MoSCoW frameworks.
*   **Outcome Guardian**: The Strategic Compass. Ensures alignment and measurable outcomes.
    *   `strategic-alignment-score`: Rates proposed features 1-5 on how well they support specific Company Objectives.
    *   `generate-outcome-draft`: Drafts high-quality, Outcome-based Objectives and Key Results (OKRs).

## 🛠️ How to Use
1.  **Open your IDE** to this workspace.
2.  **Open the Chat** with the `Chief of Staff` agent.
3.  **Prompt**: "Help me with..."
    *   *"...analyzing a competitor."* -> Routes to Market Sentinel.
    *   *"...planning the Q3 roadmap."* -> Routes to Portfolio Orchestrator.
    *   *"...checking if this feature is strategic."* -> Routes to Outcome Guardian.

## 🧪 Verification
We have stress-tested the foundation:
*   ✅ **Constraint Enforcement**: Agents block features that violate `technical_constraints.md`.
*   ✅ **Strategic Alignment**: Agents reject "vanity projects" that don't match `product_strategy.md`.
*   ✅ **Ambiguity Handling**: Agents ask clarifying questions when intent is unclear.

## 🔮 Future Enhancements
TBD
