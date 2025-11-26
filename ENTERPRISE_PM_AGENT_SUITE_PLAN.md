# Implementation Plan - Enterprise PM Agent Suite (Detailed Workflows)

Create a comprehensive suite of AI agents for Enterprise Product Managers, structured around custom modules tailored to the PM persona. This plan ensures **2+ agents per module** and **2+ workflows per agent**, with a Chief Orchestrator.

## User Review Required
> [!IMPORTANT]
> This plan uses a **Custom PM Module Structure** (Strategy, Insights, Definition, Execution, Go-to-Market (GTM), Leadership & Excellence). It includes **24 Specialized Agents** and detailed descriptions for every workflow.
> **The Codex**: The plan includes creating a shared context layer called "The Codex". Please review the proposed categories below and suggest any additions.

## Proposed Changes

### Execution Strategy: The "Draft-Review" Loop
To avoid "blank page" fatigue, we will use a **Draft-Review** methodology for **ALL Modules (0-6)**.
1.  **Proposal**: I will generate a **Truly Comprehensive Specification** for each agent, one by one.
    -   **Detailed Definition**: For every field (Type, Icon, Personality, Workflow Config, etc.), I will provide **Draft Examples**, **Rationale** for the choice, and an **Audition/Example Output** to demonstrate the behavior.
    -   **Agent Profile**: Role, Type (Simple/Expert/Module), Icon, Personality (with Rationale), Principles (with Rationale), Critical Actions (with Rationale).
    -   **Workflow Specs**: Goal, Configuration, Interaction Style, Step Logic, Outputs, Validation.
    -   **[NEW] Copy-Paste Readiness**: Explicit definition of how the output can be immediately used (e.g., "Slack Block", "Markdown Snippet").
    -   **[NEW] The Audition**: A simulated output scenario to judge tone and quality.
2.  **Review**: You approve or tweak the specific details.
3.  **Build**: I create the files only after approval.

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

- **Workflows:**
    - `route-request`: The single entry point. Analyzes user intent and dispatches to specialist agents. **[NEW]** If intent is unclear or user asks for help, proactively presents a "Capabilities Menu" of what the suite can do.

    - `daily-briefing`: Reviews all active workflows and project states to suggest prioritized actions the PM should take today.

    - `update-codex`: Interviews the user to populate or update The Codex files (e.g., "Tell me about your users..." -> updates `user_personas.md`).


#### [NEW] [chain-commander.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/chain-commander.md)
- **Role:** Automates multi-step handoffs between specialist agents to execute complex end-to-end processes.

- **Workflows:**
    - `feature-factory-chain`: Orchestrates the flow from Opportunity (Market Sentinel) -> Validation (Strategic Account Advocate) -> Definition (Requirement Architect) -> **[APPROVAL GATE]** -> Feasibility (Technical Partner).

    - `release-train-chain`: Orchestrates the flow from Spec (Agile Captain) -> Cleanup (Bugs & Tech Debt Steward) -> **[APPROVAL GATE]** -> Comms (Release Communicator) -> Notification (Stakeholder Liaison).

    - `strategy-refresh-chain`: Orchestrates the flow from Review (Outcome Guardian) -> Roadmap Update (Portfolio & Release Orchestrator) -> **[APPROVAL GATE]** -> Alignment (Session Facilitator).


#### [NEW] [pm-toolkit.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/pm-toolkit.md)
- **Role:** Provides universal PM utilities and best practices applicable across all workflows.

- **Workflows:**
    - `document-quality-audit`: Reviews any text for clarity, tone, and formatting errors.

    - `meeting-minutes-synthesizer`: Takes raw meeting notes or transcripts and generates structured summaries with action items, decisions, and key discussion points.

    - `decision-framework-selector`: Recommends the appropriate decision-making framework (RACI, DACI, Weighted Scoring, etc.) based on the type of decision and context.


#### [NEW] [session-facilitator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/session-facilitator.md)
- **Role:** Orchestrates collaboration between specialized agents to generate unified workshop deliverables, ensuring all perspectives are integrated into final decisions.

- **Workflows:**
    - `roadmap-planning`: Convenes Market Sentinel, Portfolio & Release Orchestrator, Outcome Guardian, Strategic Account Advocate, Data & Feedback Strategist, and Compliance Officer to align on strategic objectives and roadmap priorities.

    - `release-planning`: Orchestrates Market Sentinel, Portfolio & Release Orchestrator, Outcome Guardian, Strategic Account Advocate, Data & Feedback Strategist, Requirement Architect, Compliance Officer, Agile Captain, and Bugs & Tech Debt Steward to plan and validate release scope.

    - `design-engineering-handoff`: Coordinates UX Designer, Requirement Architect, and Agile Captain to ensure smooth transition from design to development with clear acceptance criteria.


### Module 1: Strategy & Market
*Focus: The "Why" and "When" - Strategy, market intelligence, and portfolio alignment.*

#### [NEW] [market-sentinel.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/market-sentinel.md)
- **Role:** Continuous competitive intelligence and market trend analysis.

- **Workflows:**
    - `competitor-capability-comparison`: Analyzes and compares specific product capabilities against competitors to identify functional gaps and differentiation opportunities.

    - `pmf-calibration-check`: Evaluates Product-Market Fit using retention curves, survey scores (Sean Ellis test), and win/loss signals.

    - `market-opportunity-scanner`: Identifies unaddressed market problems ("white space") based on user forums and analyst reports.


#### [NEW] [portfolio-release-orchestrator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/portfolio-release-orchestrator.md)
- **Role:** Manages dependencies, timelines, and release prioritization across multiple product teams.

- **Workflows:**
    - `roadmap-sync`: Merges individual team roadmaps into a master portfolio view for executives.

    - `release-scenario-planner`: Models different release packages (e.g., "Aggressive Scope" vs. "Fixed Date") while analyzing cross-team dependencies to help make trade-off decisions.

    - `prioritization-matrix`: Ranks proposed features using RICE (Reach, Impact, Confidence, Effort) or Value/Effort scoring.


#### [NEW] [outcome-guardian.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/outcome-guardian.md)
- **Role:** Ensures roadmap items trace back to strategic objectives.

- **Workflows:**
    - `strategic-alignment-score`: Rates proposed features based on how well they move specific Key Performance Indicators (KPIs).

    - `generate-outcome-draft`: Drafts new Strategic Outcomes and Metrics based on company strategy documents.


### Module 2: User & Data Insights
*Focus: The "Who" and "What" - Deep understanding of users and data.*

#### [NEW] [strategic-account-advocate.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/strategic-account-advocate.md)
- **Role:** Champions the needs of strategic accounts and Customer Advisory Boards (CAB), ensuring their voice shapes the product roadmap.

- **Workflows:**
    - `strategic-feature-audit`: Analyzes the status of delivered vs. open feature requests for specific strategic accounts to demonstrate value or identify risks.

    - `relationship-health-scorecard`: Evaluates the overall health of a strategic relationship based on engagement, sentiment, and roadmap alignment.


#### [NEW] [data-feedback-strategist.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/data-feedback-strategist.md)
- **Role:** Defines metrics, synthesizes performance data, and processes raw customer feedback.

- **Workflows:**
    - `analyze-data-source`: Ingests quantitative (CSV) or qualitative (text) data to extract trends, sentiment, or feature requests.

    - `define-success-plan`: Defines success metrics (HEART: Happiness, Engagement, Adoption, Retention, Task Success) and generates the corresponding technical instrumentation plan.

    - `design-experiment`: Designs A/B tests, rollout strategies, and validation criteria to prove a hypothesis.


#### [NEW] [persona-simulator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/persona-simulator.md)
- **Role:** Adopts stakeholder personas to test ideas early.

- **Workflows:**
    - `create-new-persona`: Generates a detailed persona profile based on user data and demographics.

    - `simulate-perspective`: Adopts a specific persona (e.g., CISO, Admin) to critique a feature or design.




### Module 3: Product Definition
*Focus: The Solution - Detailed requirements, design, and compliance.*

#### [NEW] [requirement-architect.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/requirement-architect.md)
- **Role:** Drafts enterprise-grade Product Requirements Documents (PRDs).

- **Workflows:**
    - `generate-enterprise-prd`: Drafts requirements including mandatory sections for Role-Based Access Control (RBAC), Audit Logs, and SSO.

    - `edge-case-explorer`: Proactively asks "What if?" questions to identify missing requirements.

    - `generate-visualization`: Creates diagrams (flowcharts, sequence, Entity Relationship Diagram (ERD)) using tools like Mermaid.js to include in the PRD.


#### [NEW] [ux-designer.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/ux-designer.md)
- **Role:** Visualizes concepts and ensures user-centric design.

- **Workflows:**
    - `generate-wireframe-concepts`: Creates low-fidelity wireframe descriptions or ASCII mockups for a feature.

    - `generate-high-fidelity-mockup`: Generates high-fidelity visual mockups that follow a specific design language.

    - `usability-test-script`: Generates a script for user testing sessions based on the design.




#### [NEW] [compliance-officer.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/compliance-officer.md)
- **Role:** Pre-engineering compliance checks.

- **Workflows:**
    - `security-review-prep`: Pre-fills security questionnaires based on the proposed feature architecture.

    - `accessibility-audit-plan`: Generates a checklist for WCAG 2.1 compliance for the design team.

    - `regulatory-watch`: Scans for new compliance standards (GDPR, HIPAA) that impact the roadmap.


### Module 4: Engineering & Execution
*Focus: The Build - Managing the engineering relationship and output.*

#### [NEW] [agile-captain.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/agile-captain.md)
- **Role:** Scrum Master/Product Owner (PO) hybrid for sprint management.

- **Workflows:**
    - `prd-to-epic-breakdown`: Analyzes a Product Requirements Document (PRD) and generates Epics following a standardized template, ensuring completeness and quality standards are met.

    - `epic-to-story-breakdown`: Decomposes Epics into User Stories following a standardized template, ensuring all "Definition of Ready" criteria are met.

    - `sprint-planning-prep`: Suggests a sprint backlog based on team velocity, current priorities, and active blockers.




#### [NEW] [bugs-tech-debt-steward.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/bugs-tech-debt-steward.md)
- **Role:** Manages the balance between new features, bug fixes, and technical health.

- **Workflows:**
    - `bug-triage-and-tracking`: Reviews open bug tickets, categorizes them by severity, and tracks their age and resolution status.

    - `refactor-roi-calculator`: Helps engineers articulate the business value of a refactor using Return on Investment (ROI) analysis.

    - `technical-debt-audit`: Scans the backlog for tech debt items and categorizes them by risk.


#### [NEW] [technical-partner.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/technical-partner.md)
- **Role:** Simulates the perspective of a Senior Architect and Lead Developer to provide early technical feedback.

- **Workflows:**
    - `architecture-feasibility-check`: Reviews a PRD or feature concept to identify architectural risks, scalability concerns, and necessary system changes.

    - `implementation-strategy-advisor`: Suggests the technical approach, potential refactoring needs, and sequencing of tasks (Lead Dev perspective).

    - `technical-concept-explainer`: Explains complex engineering terms or constraints to help the PM understand technical pushback.


### Module 5: Go-to-Market & Stakeholders
*Focus: The Launch - Taking the product to market and keeping people informed.*

#### [NEW] [value-prop-evangelist.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/value-prop-evangelist.md)
- **Role:** Translates features into business outcomes.

- **Workflows:**
    - `battle-card-generator`: Creates one-pagers for sales to use against specific competitors.

    - `roi-calculator-builder`: Creates logic for spreadsheets/tools for sales to prove value using Return on Investment calculations.

    - `value-story-generator`: Brainstorms compelling customer stories and real-life end-to-end user flows that demonstrate the value delivered by new features or releases.


#### [NEW] [release-communicator.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/release-communicator.md)
- **Role:** Manages release information flow.

- **Workflows:**
    - `multi-tier-release-notes`: Writes three versions of release notes: Exec (value), Admin (config), User (usage).

    - `internal-enablement-brief`: Generates the "What you need to know" doc for Customer Success and Support.


#### [NEW] [stakeholder-liaison.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/stakeholder-liaison.md)
- **Role:** Manages updates for internal/external stakeholders.

- **Workflows:**
    - `generate-stakeholder-update`: Creates tailored status updates for specific stakeholder groups in various formats (emails, Slack messages, one-page documents, executive summaries).

    - `manage-stakeholder-registry`: Maintains a list of who needs to know what and when.

    - `executive-briefing-prep`: Creates a concise slide deck outline for an executive review.


### Module 6: Leadership & Excellence
*Focus: Team leadership, influence, personal growth, and quality standards.*

#### [NEW] [team-dynamics-coach.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/team-dynamics-coach.md)
- **Role:** Improves team health, collaboration, and interpersonal dynamics.

- **Workflows:**
    - `facilitate-retrospective`: Guides the team through a "Start, Stop, Continue" or similar retro format.

    - `incident-post-mortem`: Guides the team through a root cause analysis (5 Whys) after an incident.

    - `1-on-1-prep`: Generates personalized discussion topics and questions for individual team member check-ins based on their recent work and contributions.

    - `difficult-conversation-guide`: Provides frameworks, talking points, and scripts for navigating team conflicts, delivering bad news, saying "no," or addressing performance issues.


#### [NEW] [influence-persuasion-advisor.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/influence-persuasion-advisor.md)
- **Role:** Helps PMs navigate organizational politics and build stakeholder buy-in.

- **Workflows:**
    - `stakeholder-influence-map`: Identifies key decision-makers and influencers for a specific initiative and suggests engagement strategies.

    - `objection-handler`: Anticipates common objections to a proposal and generates counter-arguments or data points.

    - `coalition-builder`: Suggests who to align with internally to build support for a controversial or risky decision.


#### [NEW] [pm-career-mentor.md](file:///c:/Users/Sickl/.gemini/antigravity/scratch/PMAgents/BMAD-METHOD/.bmad/custom/agents/pm-career-mentor.md)
- **Role:** Supports personal development and career advancement for the PM.

- **Workflows:**
    - `skill-gap-analysis`: Identifies areas for growth based on the PM's current work patterns and industry trends.

    - `career-narrative-builder`: Helps craft compelling stories about impact and achievements for performance reviews or job interviews.

    - `networking-strategy`: Suggests internal/external connections to build based on career goals.

    - `leadership-development-plan`: Creates a personalized roadmap for developing specific leadership competencies.

    - `pm-mentoring-guide`: Provides frameworks, discussion topics, and growth plans for mentoring junior or transitioning PMs.


## Verification Plan

### Manual Verification
- Verify that the folder structure matches the 7 custom modules (0-6).
- Verify that all 24 agents are present and correctly configured.
- Verify that every agent has at least 2 workflows.

## Quality Assurance Checklist
- [ ] **Module 0: Orchestration**
    - [ ] Chief of Staff (Agent & Workflows)
    - [ ] Chain Commander (Agent & Workflows)
    - [ ] PM Toolkit (Agent & Workflows)
    - [ ] Session Facilitator (Agent & Workflows)
- [ ] **Module 1: Strategy & Market**
    - [ ] Market Sentinel (Agent & Workflows)
    - [ ] Portfolio & Release Orchestrator (Agent & Workflows)
    - [ ] Outcome Guardian (Agent & Workflows)
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
