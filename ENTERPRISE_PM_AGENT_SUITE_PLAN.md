# Implementation Plan - Enterprise PM Agent Suite (Detailed Workflows)

Create a comprehensive suite of AI agents for Enterprise Product Managers, structured around custom modules tailored to the PM persona. This plan ensures **2+ agents per module** and **2+ workflows per agent**, with a Chief Orchestrator.

## User Review Required
> [!IMPORTANT]
> This plan uses a **Custom PM Module Structure** (Strategy, Insights, Definition, Execution, Go-to-Market (GTM), Leadership & Excellence). It includes **24 Specialized Agents** and detailed descriptions for every workflow.
> **The Codex**: The plan includes creating a shared context layer called "The Codex". Please review the proposed categories below and suggest any additions.

## Proposed Changes

### Execution Strategy: The "Draft-Review" Loop
To avoid "blank page" fatigue, we will use a **Draft-Review** methodology for **ALL Modules (0-6)**.
1.  **Proposal**: I will generate a complete draft of the agent's personality, tone, and workflow logic based on "Best Practice" defaults.
2.  **Reasoning**: I will explicitly state *why* I chose those defaults (e.g., "Chosen 'Skeptical' tone for Market Sentinel to avoid false positives").
3.  **Review**: You simply approve or tweak the draft.

### Phase 1: Foundation & Pilot (Vertical Slice)
*Goal: Build a working skeleton with Module 0 and Module 1 to validate architecture immediately.*
- **Module 0 (Orchestration)**: Proposal -> Review -> Build.
- **Module 1 (Strategy)**: Proposal -> Review -> Build.
- **[NEW] Codex Bootstrapper**: A workflow for `Chief of Staff` that interviews the user to populate `product_strategy.md` and `company_mission.md` automatically.
- **Verify**: Test the full chain: User -> Chief of Staff -> Market Sentinel -> Output.

### Phase 2: The Draft-Review Loop (Modules 2-6)
*Goal: Systematically build out the remaining specialist agents.*
- For each module, we will follow the **Proposal -> Review -> Build -> Verify** cycle.

### Phase 3: Integration & QA
*Goal: Connect the dots and ensure stability.*
- **[NEW] Automated Roll Call**: A script that iterates through every agent to verify:
    1.  It loads successfully.
    2.  It can read from The Codex.
    3.  It responds to a basic "Who are you?" prompt.

### The Codex (Shared Context Layer)
*Focus: Centralized knowledge base for all agents to ensure alignment.*

#### [NEW] Context Files
Create a `.bmad/custom/context/` directory with the following files. **User input required on categories:**
- `company_mission.md`: Vision, Mission, Values.
- `product_strategy.md`: Current OKRs, Strategic Pillars.
- `user_personas.md`: Detailed user profiles.
- `technical_constraints.md`: Tech stack, "No-Go" zones.
- `brand_voice.md`: Tone, Style Guide.
- `stakeholder_map.md`: Key execs and their preferences.

#### [NEW] README.md
Create a `README.md` file in the root directory to document the project scope, architecture, and usage.
- **Project Overview**: Explanation of the 7-module structure and 24-agent suite.
- **Getting Started**: Step-by-step guide to installing the suite, populating The Codex, and running the first workflow.
- **The Codex**: Guide on how to populate the shared context layer.
- **Feature Roadmap Considerations**:
    - **Self-Correction Loops**: Future enhancement to have `PM Toolkit` automatically audit chain outputs before passing to the next step.
    - **Proactive Context Checks**: Future enhancement for `Chief of Staff` to validate requests against `technical_constraints.md` before execution.
    - **"Lite" Mode**: Future enhancement to provide fallback "best practice" context if The Codex files are empty.

### Module 0: Orchestration
*Focus: Routing, universal utilities, and multi-agent collaboration.*

#### [NEW] [chief-of-staff.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/chief-of-staff.md)
- **Role:** The primary interface for the user. Acts as a facade for the entire suite, intelligently routing requests and clarifying intent.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `route-request`: Analyzes user intent, asks clarifying questions if needed, and dispatches the request to the correct single agent or combination of agents.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `daily-briefing`: Reviews all active workflows and project states to suggest prioritized actions the PM should take today.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `update-codex`: Interviews the user to populate or update The Codex files (e.g., "Tell me about your users..." -> updates `user_personas.md`).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [workflow-orchestrator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/workflow-orchestrator.md)
- **Role:** Automates multi-step handoffs between specialist agents to execute complex end-to-end processes.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `feature-factory-chain`: Orchestrates the flow from Opportunity (Market Sentinel) -> Validation (Strategic Account Advocate) -> Definition (Requirement Architect) -> **[APPROVAL GATE]** -> Feasibility (Technical Partner).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `release-train-chain`: Orchestrates the flow from Spec (Agile Captain) -> Cleanup (Bugs & Tech Debt Steward) -> **[APPROVAL GATE]** -> Comms (Release Communicator) -> Notification (Stakeholder Liaison).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `strategy-refresh-chain`: Orchestrates the flow from Review (OKR Guardian) -> Roadmap Update (Portfolio & Release Orchestrator) -> **[APPROVAL GATE]** -> Alignment (Session Facilitator).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [pm-toolkit.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/pm-toolkit.md)
- **Role:** Provides universal PM utilities and best practices applicable across all workflows.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `document-quality-audit`: Reviews any text for clarity, tone, and formatting errors.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `meeting-minutes-synthesizer`: Takes raw meeting notes or transcripts and generates structured summaries with action items, decisions, and key discussion points.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `decision-framework-selector`: Recommends the appropriate decision-making framework (RACI, DACI, Weighted Scoring, etc.) based on the type of decision and context.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [session-facilitator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/session-facilitator.md)
- **Role:** Orchestrates multi-agent collaborative sessions for complex cross-functional activities.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `roadmap-planning`: Convenes Market Sentinel, Portfolio & Release Orchestrator, OKR Guardian, Strategic Account Advocate, Data & Feedback Strategist, and Compliance Officer to align on strategic objectives and roadmap priorities.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `release-planning`: Orchestrates Market Sentinel, Portfolio & Release Orchestrator, OKR Guardian, Strategic Account Advocate, Data & Feedback Strategist, Requirement Architect, Compliance Officer, Agile Captain, and Bugs & Tech Debt Steward to plan and validate release scope.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `design-engineering-handoff`: Coordinates UX Designer, Requirement Architect, and Agile Captain to ensure smooth transition from design to development with clear acceptance criteria.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

### Module 1: Strategy & Market
*Focus: The "Why" and "When" - Strategy, market intelligence, and portfolio alignment.*

#### [NEW] [market-sentinel.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/market-sentinel.md)
- **Role:** Continuous competitive intelligence and market trend analysis.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `competitor-capability-comparison`: Analyzes and compares specific product capabilities against competitors to identify functional gaps and differentiation opportunities.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `pmf-calibration-check`: Evaluates Product-Market Fit using retention curves, survey scores (Sean Ellis test), and win/loss signals.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `market-opportunity-scanner`: Identifies unaddressed market problems ("white space") based on user forums and analyst reports.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [portfolio-release-orchestrator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/portfolio-release-orchestrator.md)
- **Role:** Manages dependencies, timelines, and release prioritization across multiple product teams.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `roadmap-sync`: Merges individual team roadmaps into a master portfolio view for executives.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `release-scenario-planner`: Models different release packages (e.g., "Aggressive Scope" vs. "Fixed Date") while analyzing cross-team dependencies to help make trade-off decisions.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `prioritization-matrix`: Ranks proposed features using RICE (Reach, Impact, Confidence, Effort) or Value/Effort scoring.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [okr-guardian.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/okr-guardian.md)
- **Role:** Ensures roadmap items trace back to strategic objectives.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `strategic-alignment-score`: Rates proposed features based on how well they move specific Key Performance Indicators (KPIs).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `generate-okr-draft`: Drafts new Objectives and Key Results (OKRs) based on company strategy documents.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

### Module 2: User & Data Insights
*Focus: The "Who" and "What" - Deep understanding of users and data.*

#### [NEW] [strategic-account-advocate.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/strategic-account-advocate.md)
- **Role:** Champions the needs of strategic accounts and Customer Advisory Boards (CAB), ensuring their voice shapes the product roadmap.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `strategic-feature-audit`: Analyzes the status of delivered vs. open feature requests for specific strategic accounts to demonstrate value or identify risks.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `relationship-health-scorecard`: Evaluates the overall health of a strategic relationship based on engagement, sentiment, and roadmap alignment.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [data-feedback-strategist.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/data-feedback-strategist.md)
- **Role:** Defines metrics, synthesizes performance data, and processes raw customer feedback.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `analyze-data-source`: Ingests quantitative (CSV) or qualitative (text) data to extract trends, sentiment, or feature requests.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `define-success-plan`: Defines success metrics (HEART: Happiness, Engagement, Adoption, Retention, Task Success) and generates the corresponding technical instrumentation plan.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `design-experiment`: Designs A/B tests, rollout strategies, and validation criteria to prove a hypothesis.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [persona-simulator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/persona-simulator.md)
- **Role:** Adopts stakeholder personas to test ideas early.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `create-new-persona`: Generates a detailed persona profile based on user data and demographics.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `simulate-perspective`: Adopts a specific persona (e.g., CISO, Admin) to critique a feature or design.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]



### Module 3: Product Definition
*Focus: The Solution - Detailed requirements, design, and compliance.*

#### [NEW] [requirement-architect.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/requirement-architect.md)
- **Role:** Drafts enterprise-grade Product Requirements Documents (PRDs).
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `generate-enterprise-prd`: Drafts requirements including mandatory sections for Role-Based Access Control (RBAC), Audit Logs, and SSO.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `edge-case-explorer`: Proactively asks "What if?" questions to identify missing requirements.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `generate-visualization`: Creates diagrams (flowcharts, sequence, Entity Relationship Diagram (ERD)) using tools like Mermaid.js to include in the PRD.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [ux-designer.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/ux-designer.md)
- **Role:** Visualizes concepts and ensures user-centric design.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `generate-wireframe-concepts`: Creates low-fidelity wireframe descriptions or ASCII mockups for a feature.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `generate-high-fidelity-mockup`: Generates high-fidelity visual mockups that follow a specific design language.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `usability-test-script`: Generates a script for user testing sessions based on the design.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]



#### [NEW] [compliance-officer.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/compliance-officer.md)
- **Role:** Pre-engineering compliance checks.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `security-review-prep`: Pre-fills security questionnaires based on the proposed feature architecture.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `accessibility-audit-plan`: Generates a checklist for WCAG 2.1 compliance for the design team.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `regulatory-watch`: Scans for new compliance standards (GDPR, HIPAA) that impact the roadmap.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

### Module 4: Engineering & Execution
*Focus: The Build - Managing the engineering relationship and output.*

#### [NEW] [agile-captain.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/agile-captain.md)
- **Role:** Scrum Master/Product Owner (PO) hybrid for sprint management.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `prd-to-epic-breakdown`: Analyzes a Product Requirements Document (PRD) and generates Epics following a standardized template, ensuring completeness and quality standards are met.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `epic-to-story-breakdown`: Decomposes Epics into User Stories following a standardized template, ensuring all "Definition of Ready" criteria are met.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `sprint-planning-prep`: Suggests a sprint backlog based on team velocity, current priorities, and active blockers.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]



#### [NEW] [bugs-tech-debt-steward.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/bugs-tech-debt-steward.md)
- **Role:** Manages the balance between new features, bug fixes, and technical health.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `bug-triage-and-tracking`: Reviews open bug tickets, categorizes them by severity, and tracks their age and resolution status.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `refactor-roi-calculator`: Helps engineers articulate the business value of a refactor using Return on Investment (ROI) analysis.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `technical-debt-audit`: Scans the backlog for tech debt items and categorizes them by risk.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [technical-partner.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/technical-partner.md)
- **Role:** Simulates the perspective of a Senior Architect and Lead Developer to provide early technical feedback.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `architecture-feasibility-check`: Reviews a PRD or feature concept to identify architectural risks, scalability concerns, and necessary system changes.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `implementation-strategy-advisor`: Suggests the technical approach, potential refactoring needs, and sequencing of tasks (Lead Dev perspective).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `technical-concept-explainer`: Explains complex engineering terms or constraints to help the PM understand technical pushback.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

### Module 5: Go-to-Market & Stakeholders
*Focus: The Launch - Taking the product to market and keeping people informed.*

#### [NEW] [value-prop-evangelist.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/value-prop-evangelist.md)
- **Role:** Translates features into business outcomes.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `battle-card-generator`: Creates one-pagers for sales to use against specific competitors.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `roi-calculator-builder`: Creates logic for spreadsheets/tools for sales to prove value using Return on Investment calculations.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `value-story-generator`: Brainstorms compelling customer stories and real-life end-to-end user flows that demonstrate the value delivered by new features or releases.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [release-communicator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/release-communicator.md)
- **Role:** Manages release information flow.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `multi-tier-release-notes`: Writes three versions of release notes: Exec (value), Admin (config), User (usage).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `internal-enablement-brief`: Generates the "What you need to know" doc for Customer Success and Support.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [stakeholder-liaison.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/stakeholder-liaison.md)
- **Role:** Manages updates for internal/external stakeholders.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `generate-stakeholder-update`: Creates tailored status updates for specific stakeholder groups in various formats (emails, Slack messages, one-page documents, executive summaries).
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `manage-stakeholder-registry`: Maintains a list of who needs to know what and when.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `executive-briefing-prep`: Creates a concise slide deck outline for an executive review.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

### Module 6: Leadership & Excellence
*Focus: Team leadership, influence, personal growth, and quality standards.*

#### [NEW] [team-dynamics-coach.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/team-dynamics-coach.md)
- **Role:** Improves team health, collaboration, and interpersonal dynamics.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `facilitate-retrospective`: Guides the team through a "Start, Stop, Continue" or similar retro format.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `incident-post-mortem`: Guides the team through a root cause analysis (5 Whys) after an incident.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `1-on-1-prep`: Generates personalized discussion topics and questions for individual team member check-ins based on their recent work and contributions.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `difficult-conversation-guide`: Provides frameworks, talking points, and scripts for navigating team conflicts, delivering bad news, saying "no," or addressing performance issues.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [influence-persuasion-advisor.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/influence-persuasion-advisor.md)
- **Role:** Helps PMs navigate organizational politics and build stakeholder buy-in.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `stakeholder-influence-map`: Identifies key decision-makers and influencers for a specific initiative and suggests engagement strategies.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `objection-handler`: Anticipates common objections to a proposal and generates counter-arguments or data points.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `coalition-builder`: Suggests who to align with internally to build support for a controversial or risky decision.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

#### [NEW] [pm-career-mentor.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/pm-career-mentor.md)
- **Role:** Supports personal development and career advancement for the PM.
- **Type:** [Simple/Expert/Module]
- **Icon:** [Emoji]
- **Personality/Tone:** [To be defined]
- **Core Principles:** [To be defined]
- **Critical Actions:** [To be defined]
- **Workflows:**
    - `skill-gap-analysis`: Identifies areas for growth based on the PM's current work patterns and industry trends.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `career-narrative-builder`: Helps craft compelling stories about impact and achievements for performance reviews or job interviews.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `networking-strategy`: Suggests internal/external connections to build based on career goals.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `leadership-development-plan`: Creates a personalized roadmap for developing specific leadership competencies.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]
    - `pm-mentoring-guide`: Provides frameworks, discussion topics, and growth plans for mentoring junior or transitioning PMs.
        - **Core Configuration:** [Description, Standalone]
        - **Interaction Style:** [Intent/Prescriptive, Interactivity Level]
        - **Step Logic & Flow:** [Goals, Branching, Repetition]
        - **Outputs & Templates:** [Artifacts, Variables]
        - **Validation:** [Success Criteria, Checklists]

## Verification Plan

### Manual Verification
- Verify that the folder structure matches the 7 custom modules (0-6).
- Verify that all 24 agents are present and correctly configured.
- Verify that every agent has at least 2 workflows.

## Quality Assurance Checklist
- [ ] **Module 0: Orchestration**
    - [ ] Chief of Staff (Agent & Workflows)
    - [ ] Workflow Orchestrator (Agent & Workflows)
    - [ ] PM Toolkit (Agent & Workflows)
    - [ ] Session Facilitator (Agent & Workflows)
- [ ] **Module 1: Strategy & Market**
    - [ ] Market Sentinel (Agent & Workflows)
    - [ ] Portfolio & Release Orchestrator (Agent & Workflows)
    - [ ] OKR Guardian (Agent & Workflows)
- [ ] **Module 2: User & Data Insights**
    - [ ] Strategic Account Advocate (Agent & Workflows)
    - [ ] Data & Feedback Strategist (Agent & Workflows)
    - [ ] Persona Simulator (Agent & Workflows)
- [ ] **Module 3: Product Definition**
    - [ ] Requirement Architect (Agent & Workflows)
    - [ ] UX Designer (Agent & Workflows)
    - [ ] Compliance Officer (Agent & Workflows)
- [ ] **Module 4: Engineering & Execution**
    - [ ] Agile Captain (Agent & Workflows)
    - [ ] Bugs & Tech Debt Steward (Agent & Workflows)
    - [ ] Technical Partner (Agent & Workflows)
- [ ] **Module 5: Go-to-Market & Stakeholders**
    - [ ] Value Prop Evangelist (Agent & Workflows)
    - [ ] Release Communicator (Agent & Workflows)
    - [ ] Stakeholder Liaison (Agent & Workflows)
- [ ] **Module 6: Leadership & Excellence**
    - [ ] Team Dynamics Coach (Agent & Workflows)
    - [ ] Influence & Persuasion Advisor (Agent & Workflows)
    - [ ] PM Career Mentor (Agent & Workflows)
