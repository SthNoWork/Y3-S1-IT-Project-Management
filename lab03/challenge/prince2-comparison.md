# PRINCE2 7 Alignment & Comparative Analysis · Realtime Quiz

Evaluation of the Realtime Quiz hybrid life cycle against the PRINCE2 7 project management methodology.

## 1. Mapping Matrix (Hybrid vs. PRINCE2 7 Equivalents)

| # | Realtime Quiz Hybrid Life Cycle Concept | PRINCE2 7 Process / Artifact / Role Equivalent | Functional Comparison |
| - | :--- | :--- | :--- |
| 1 | **Phase Gates ($G1$–$G4$)** | **End Stage Assessment (Managing a Stage Boundary)** | Formal decision checkpoints where the Project Board inspects stage deliverables before authorizing the next stage. |
| 2 | **Project Charter (`lab01`)** | **Project Brief & Project Initiation Documentation (PID)** | Baseline contractual document defining business justification, project scope, team roles, and initial risk assessment. |
| 3 | **Product Owner (Student A)** | **Senior User (Project Board member)** | Represents the end-user requirements, specifies operational acceptance criteria, and verifies deliverable utility. |
| 4 | **Project Manager (Dr. Alex Vance)** | **Project Manager (Directing & Managing a Project)** | Manages stage tolerances, monitors stage boundary progression, and acts as the operational interface to the board. |
| 5 | **Sponsor (Head of IT)** | **Executive (Project Board Chair)** | Holds ultimate decision-making authority, owns the Business Case, and signs off on capital and milestone commitments. |
| 6 | **Scrum Master & Developers (Students A–D)** | **Team Manager & Work Package Team (Managing Product Delivery)** | Self-organizes the technical delivery of authorized work packages within stage boundaries. |
| 7 | **Sprint Backlog & 14-day Sprint** | **Work Package (Managing Product Delivery)** | Formally agreed allocation of work defining interfaces, quality requirements, and execution timeboxes. |
| 8 | **Definition of Done (DoD)** | **Quality Register & Quality Criteria (Product Description)** | Explicit, measurable standards that every deliverable product must satisfy prior to acceptance. |
| 9 | **Tolerance Matrix (Time, Cost, Scope, Quality)** | **Project & Stage Tolerances (Manage by Exception)** | Quantified permissible variance thresholds enabling autonomous execution without unnecessary escalation. |
| 10 | **Three-Line Exception Report** | **Exception Report & Exception Plan (Escalating)** | Structured notification to the Project Board when a stage is forecast to breach agreed tolerance boundaries. |
| 11 | **Weekly Highlight Report** | **Highlight Report (Controlling a Stage)** | Regular, time-interval summary delivered by the PM to the Board covering progress, tolerance health, and risks. |
| 12 | **Stage 4 Handover & Closure** | **Closing a Project Process (End Project Report)** | Orderly decommissioning of project infrastructure, verification of user acceptance, and handover of operational assets. |

---

## 2. Governance Value Added by PRINCE2 7

PRINCE2 7 introduces rigorous **Continued Business Justification** and structured **Management by Exception**, which significantly strengthen our project governance. In purely agile student projects, teams frequently suffer from subjective drift—spending time on technologically fascinating features (e.g., in-quiz live chat or custom CSS animations) while losing sight of the core departmental business need (an automated quiz grading system to replace paper exams). By embedding PRINCE2's *Directing a Project* layer, our Project Board (Sponsor and Supervising Lecturer) establishes explicit, measurable stage gates ($G1$–$G4$) and quantified tolerance envelopes. This ensures that the team cannot silently absorb velocity losses or mask architectural failures. The formal requirement for an *Exception Report* forces immediate, objective decision-making the moment a stage boundary is threatened, preventing end-of-semester delivery crises.

---

## 3. Overhead and Bureaucracy Imposed by PRINCE2 7

Conversely, adopting full PRINCE2 7 imposes severe **process overhead and administrative weight** that would cripple a 4-student, 10-hour-per-week development team. A full-scale PRINCE2 implementation mandates 26 distinct management products, including formal *Business Case Updates*, *Issue Registers*, *Daily Logs*, *Risk Management Approaches*, *Communication Management Approaches*, and separate *Work Package Agreements* signed between the Project Manager and Team Manager. For a small team with only 80 gross hours available every two weeks, generating and maintaining this documentation would consume an estimated 25–35 % of total effort. This administrative drag would directly subtract from coding, automated test writing, and WebSocket debugging focus hours. Our tailored hybrid model avoids this trap by condensing PRINCE2's essential governance principles (tolerances, gates, and exception escalation) into lightweight Markdown checklists, leaving maximum student capacity focused on software engineering.
