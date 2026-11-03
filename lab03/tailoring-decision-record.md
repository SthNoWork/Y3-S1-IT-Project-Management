# TDR-01 · Life cycle and methodology for the Realtime Quiz project

| Metadata | Details |
| :--- | :--- |
| **Status** | Accepted |
| **Date** | 2026-10-06 |
| **Decision Makers** | Head of IT Department (Sponsor), Dr. Alex Vance (Project Manager), Student Engineering Team |
| **Consulted** | Course Supervising Faculty, Student Representative |

---

## 1. Context

The Realtime Quiz project is a 14-week software engineering capstone developing a synchronized classroom quiz application for 50 concurrent students on a single virtual server node. The project environment is constrained by non-negotiable external deadlines, specifically an approved plan by Week 3 ($G1$), an interim MVP checkpoint at Week 7 ($G2$), and a live classroom pilot at Week 14 ($G4$). While the core 8 Must features are strictly required, significant technical uncertainty surrounds WebSocket real-time broadcast latency and campus network proxy traversal. Furthermore, the 4-student development team is executing their first formal Scrum project while learning Spring Boot and WebSockets in parallel. A pure linear approach risks catastrophic late-stage failure, while pure agile lacks the governance structure required by the academic department.

---

## 2. Options Considered

1. **Option 1 · Waterfall (Predictive):** Linear progression through sequential phases (Requirements, Design, Implementation, Integration, Pilot). Scored **250 / 500** in multi-criteria analysis due to zero functional software visibility before Week 13 and severe inability to handle WebSocket architectural risks.
2. **Option 2 · Pure Scrum (Adaptive):** Completely emergent, self-organizing product delivery across 2-week iterations without up-front architecture baselines or stage gates. Scored **375 / 500**; excels in rapid feedback, but fails departmental contract milestones and creates severe role conflict for a novice student team.
3. **Option 3 · Tailored Hybrid (Selected):** Predictive initiation and architectural baselining in Weeks 1–3 ($G1$), followed by 4 timeboxed 14-day Scrum sprints in Weeks 4–11 ($G2$, $G3$), concluding with a predictive hardening and pilot release phase in Weeks 12–14 ($G4$). Scored **460 / 500**.

---

## 3. Decision

Adopt the **Tailored Hybrid Model** as the official life cycle framework for the Realtime Quiz project based on two core rationales:
1. **Early Technical De-risking with Locked Scope Floor:** Scrum iterations in Weeks 4–11 produce early, working software by Week 5 and a validated MVP by Week 7, directly mitigating the WebSocket proxy blocker risk while locking the 8 Must features (300 h) against scope creep.
2. **Compliance with Academic Governance and Budget Caps:** Four formal stage gates ($G1$–$G4$) provide the Sponsor and PM with contractual control over schedule milestones, quality thresholds, and the 200 USD cash ceiling without burdening the student developers with daily bureaucratic micro-management.

---

## 4. Consequences

### Positive Effects
- **Immediate Architectural Validation:** Live WebSocket messaging is tested and proven in working software by Week 5 rather than Week 13.
- **Predictable Milestone Control:** Academic stakeholders retain full go/no-go approval authority at defined semester evaluation points ($G1$–$G4$).
- **Flexibility for Secondary Scope:** The 204 hours of Should and Could scope are managed adaptively across Sprints 3–4 without jeopardizing the core 300-hour Must baseline.

### Negative Effects & Actionable Mitigations
- **Dual Process Overhead:** Maintaining stage-gate documentation alongside Scrum ceremonies could consume excess student development hours.  
  *Mitigation:* Pre-format lightweight templates for stage-gate reports and restrict sprint ceremonies to strict Scrum timeboxes ($\le 2$ hours per ceremony).
- **Role Conflict in Student Team:** Students acting simultaneously as Product Owner and Developers may struggle to prioritize backlog debt over new code.  
  *Mitigation:* Appoint Student A strictly as Product Owner and Student B strictly as Scrum Master; the external PM enforces the Definition of Done.
- **Sprint Slippage Threatening Stage Gates:** Accumulated technical debt in early sprints could cause the team to fail Gate $G2$ (MVP demo).  
  *Mitigation:* Enforce an 80 % automated test coverage rule in the Definition of Done and require green CI builds before any story is marked done.

---

## 5. Tailoring Matrix

| Life Cycle Area | Keep from Predictive | Keep from Agile | Drop from Standard Frameworks | Justification |
| :--- | :--- | :--- | :--- | :--- |
| **Requirements Management** | Up-front Must scope baseline (8 features / 300 h) and formal change control board for fixed sides. | Dynamic backlog prioritization for Should/Could features (204 h) managed via user stories. | Exhaustive IEEE-830 specification documents for Should/Could scope. | Guarantees delivery of core graduation requirements while allowing realistic scope shedding if velocity drops. |
| **Governance & Quality** | 4 formal stage gates ($G1$–$G4$), tolerance matrix, and external PM exception reporting. | Definition of Done, automated CI test verification, and bi-weekly Sprint Reviews. | Heavy PRINCE2 Project Board hierarchy and daily team bureaucratic paperwork. | Provides the academic sponsor with formal contractual accountability while empowering developers during the sprint. |
| **Planning & Execution** | Fixed calendar milestone dates (Weeks 3, 7, 11, 14) and 200 USD cash budget envelope. | 14-day sprint timeboxes, daily standups, and retrospective continuous improvement. | Formal Earned Value Management (EVM) tracking and sprint release planning beyond the current phase. | Student team lacks accounting tooling for EVM; sprint velocity and burndown charts provide superior empirical tracking. |

---

## 6. Phase Gates Table ($G1$–$G4$)

| Gate | Week & Date | Required Evidence (Measurable Criteria) | Decision Maker | Allowed Outcomes |
| :---: | :---: | :--- | :---: | :--- |
| **$G1$** | **Week 3**<br>(2026-10-19) | 1. Approved Project Charter and Scope Baseline (8 Must features).<br>2. Validated System Architecture and WebSocket SockJS spike prototype.<br>3. Product Backlog loaded with Sprint 1 stories meeting DoR. | PM & Sponsor | `continue`<br>`continue with changes`<br>`stop` |
| **$G2$** | **Week 7**<br>(2026-11-16) | 1. Functional MVP demonstration (FR-Q1..FR-Q4, FR-S1..FR-S8) with 0 blocking defects.<br>2. Green CI pipeline with $\ge 80\,\%$ automated unit test coverage.<br>3. Verified WebSocket latency $\le 500\text{ ms}$ under local concurrency test. | PM & Sponsor | `continue`<br>`continue with changes`<br>`repeat`<br>`stop` |
| **$G3$** | **Week 11**<br>(2026-12-14) | 1. 100 % of Must features and prioritized Should features deployed to staging VPS.<br>2. Open Day demonstration successfully completed (DR-01 scope).<br>3. Load test demonstrating 20 concurrent rooms on 2 vCPU / 2 GB RAM. | PM & Sponsor | `continue`<br>`continue with changes`<br>`repeat` |
| **$G4$** | **Week 14**<br>(2027-01-04) | 1. Successful 50-student live classroom pilot conducted with 0 critical defects.<br>2. Complete system operational runbook, API documentation, and Git repository handover.<br>3. Signed sponsor acceptance certificate and lessons learned register. | Sponsor | `continue` (close)<br>`repeat` (re-pilot) |
