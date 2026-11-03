# Scrum setup · Realtime Quiz · Sprint 1

Configuration of Scrum team roles, ceremony calendar, Definition of Ready, Definition of Done, and Sprint 1 Goal.

## 1. Roles Matrix

| Role | Person | Accountable For | Not Responsible For |
| :--- | :--- | :--- | :--- |
| **Product Owner (PO)** | Student A | Ordering and prioritizing the Product Backlog, clarifying user stories, defining acceptance criteria, and accepting/rejecting sprint increments at Sprint Review. | Estimating technical implementation effort, dictating developer task assignments, or managing course budget. |
| **Scrum Master (SM)** | Student B | Facilitating Scrum events, removing technical/organizational blockers, coaching team on agile mechanics, and maintaining the sprint burndown chart. | Prioritizing product scope, imposing architectural designs, or grading peer academic performance. |
| **Developers** | Students A, B, C, D | Sizing backlog items (Planning Poker), designing technical solutions, building working code adhering to the DoD, and maintaining CI/CD pipeline health. | Setting external phase-gate milestone dates or unilaterally cancelling sprints. |
| **Project Manager (PM)** | Dr. Alex Vance *(Lecturer)* | Academic course grading, formal stage-gate approvals ($G1$–$G4$), tolerance monitoring, and escalating exception reports to the Sponsor. | Daily task management, sizing user stories, or micromanaging sprint execution. |
| **Sponsor** | Head of IT Department | Authorizing project charter, signing off on stage-gate transitions, and formal acceptance of the final Week 14 pilot release. | Attending daily standup meetings, inspecting code pull requests, or sprint backlog management. |

### Resolution of Dual Product Owner / Developer Role Conflict
Student A holds both the Product Owner role and a Developer role due to the 4-person team constraint. To resolve structural conflicts between scope demand and capacity:
1. **Separation of Ceremonies:** During Sprint Planning, Student A presents user stories as PO, but estimates story points as an equal developer via anonymous Planning Poker.
2. **Independent Quality Verification:** Student A cannot review or approve their own pull requests; every PR requires approval from another developer and a green CI build.
3. **Capacity Guardrails:** The Scrum Master (Student B) enforces a strict velocity cap ($\le 30$ points / 80 h) to prevent the PO from overloading the sprint backlog.

---

## 2. Sprint 1 Goal

> **"Deliver an end-to-end synchronized quiz session where an instructor can launch a multiple-choice question with a live countdown timer and connected students can submit answers in real time."**

---

## 3. Sprint 1 Event Calendar (2026-10-20 to 2026-11-02)

All events respect scaled Scrum Guide 2020 timeboxes for a 2-week sprint (80 hours team capacity).

| Event | Date(s) | Time (Timebox) | Attendees | Objective |
| :--- | :--- | :--- | :--- | :--- |
| **Sprint Planning** | Tue, 2026-10-20 | 09:00–11:00 (2.0 h) | PO, SM, Devs A–D | Confirm Sprint 1 Goal, select backlog items B-01..B-07, break into tasks. |
| **Daily Scrum** | Mon–Fri (10 work days)<br>2026-10-20 to 2026-11-02 | 09:00–09:15 (15 min) | SM, Devs A–D | Inspect progress toward Sprint Goal, synchronize daily work, flag blockers. |
| **Backlog Refinement** | Wed, 2026-10-28 | 14:00–15:00 (1.0 h) | PO, SM, Devs A–D | Clarify acceptance criteria and estimate candidate stories for Sprint 2. |
| **Sprint Review** | Mon, 2026-11-02 | 15:00–16:30 (1.5 h) | PO, SM, Devs, PM, Sponsor | Live demonstration of synchronized quiz session increment; gather feedback. |
| **Sprint Retrospective**| Mon, 2026-11-02 | 16:45–17:45 (1.0 h) | PO, SM, Devs A–D | Inspect sprint processes, identify bottlenecks, adopt 2 actionable improvements. |

---

## 4. Definition of Ready (DoR)

A user story is considered **Ready** for sprint backlog selection when all 5 conditions are fulfilled:
1. **Functional Requirement Traceability:** Mapped to a valid requirement identifier in the project baseline (e.g., `FR-Q1`, `FR-S1`).
2. **Given/When/Then Acceptance Criteria:** Minimum of two testable scenarios specified in standard Gherkin format.
3. **Team Sized:** Estimated by the development team using Fibonacci points ($\le 8$ story points).
4. **Dependencies Resolved:** All technical, architectural, and schema prerequisites are identified and unblocked.
5. **Interface Contract / UI Sketch:** A layout wireframe, UI component sketch, or REST/WebSocket JSON schema is attached.

---

## 5. Definition of Done (DoD)

A backlog item is considered **Done** and releasable only when all generic criteria are met:
1. **Automated Unit Tests Pass:** 100 % of unit test suite passes green without failures (*CI-verified*).
2. **Code Coverage Met:** Automated line test coverage is $\ge 80\,\%$ as measured by JaCoCo (*CI-verified*).
3. **Static Analysis Clean:** Zero critical or high-severity vulnerabilities or code smells reported by SonarQube / linter (*CI-verified*).
4. **Clean Build:** Production package compiles without warnings on clean Docker build (*CI-verified*).
5. **Peer Review Approved:** Pull request reviewed and approved by at least one other developer.
6. **Code Style Compliant:** Source code adheres to project formatting rules and naming conventions.
7. **Clean Merge:** Feature branch successfully rebased and merged into `develop` without conflicts.
8. **Staging Verified:** Increment deployed and manually smoke-tested in the local staging environment.
9. **PO Acceptance:** Product Owner inspects the functionality and signs off against all acceptance criteria.
