# Post-mortem: CampusPay Wallet Failure (2026)

## 1. Timeline and sources

| # | When | Event | Source |
|---|------|-------|--------|
| 1 | Month 1 (February) | University IT is requested by the Head of Finance via email to build a cashless payment app for canteen lunches and library fines within one semester; no formal project charter is drafted. | Fictional case from Lab-01 |
| 2 | Month 2 (March) | The lead software developer is assigned as dual-role project manager and sole programmer, working without project governance or steering committee oversight. | Fictional case from Lab-01 |
| 3 | Month 3 (April) | An informal campus survey prompts unvetted scope expansion; bus ticketing and parking fee payments are added without budget, schedule adjustment, or architecture review. | Fictional case from Lab-01 |
| 4 | Month 5 (July) | Development proceeds in technical isolation; progress is verbally reported as "on schedule" based solely on completed application code without hardware integration. | Fictional case from Lab-01 |
| 5 | Month 6 (August) | The application is pushed directly to the production server ahead of the September deadline without end-to-end load testing or staging validation on campus card terminals. | Fictional case from Lab-01 |
| 6 | Month 7 (September 1) | Go-live launch day disaster: physical canteen card terminals reject 40% of transactions, queues double during lunch hour, and the server crashes under peak concurrent traffic. | Fictional case from Lab-01 |
| 7 | Month 7 (September 4) | The university withdraws the CampusPay application after three days of severe operational disruption, student outcry, and cashier reconciliation failures. | Fictional case from Lab-01 |
| 8 | Month 12 (February) | The system relaunches five months behind schedule, heavily rescoped to cover canteen payments only, after costly architectural redesign and emergency remediation. | Fictional case from Lab-01 |

## 2. Classification and organisation
- **Project vs. Programme:** Originally conceived as a small, single IT project (canteen payments and library fines). However, when parking and municipal bus ticketing integrations were bolted on, it effectively morphed into an uncoordinated, multi-system programme. Because each distinct domain required separate external financial clearing and physical hardware integration, treating them as an unbudgeted single project doomed the initiative.
- **Structure and PM Authority:** The project manager operated inside a weak functional university hierarchy with virtually zero project authority. The lead developer had to write code while nominally managing the project, possessing no formal authority to refuse stakeholder scope additions, enforce change control, or mandate operational cooperation from canteen management.
- **Sponsor, Charter, and PMO:** There was no Project Management Office (PMO), no formal project charter, and no true executive sponsor. The Head of Finance was an "absentee sponsor" who initiated the project with a casual email request but never attended progress reviews, signed off on scope baselines, or provided political defense against scope creep.

## 3. Success criteria
- **Stated Success Criteria:** A single, simplistic schedule milestone: "Launch in September".
- **Missing Measurable Criteria:**
  - *Reliability & Accuracy:* Transaction authorization success rate >= 99.5%; terminal rejection rate < 0.1%.
  - *Performance & Capacity:* Payment response time <= 1.5 seconds under peak lunch load of 50 concurrent transactions per minute.
  - *Quality Gates:* Zero blocking defects in terminal communication and 100% reconciliation accuracy between app ledger and bank gateway.
- **Ignored Wider Dimensions:**
  - *Benefits Realization:* No metrics to measure queue reduction time, canteen revenue throughput, or student satisfaction.
  - *User Experience:* No usability testing with real students holding smartphones while ordering in a noisy cafeteria line.
  - *Operational Readiness:* Canteen cashiers received zero operational training, no error-code cheat sheets, and no offline fallback procedure for declined payments.
  - *Team Sustainability:* The lead developer was subjected to extreme burnout and role conflict from attempting to manage, design, and code the entire system alone.

## 4. Process groups and knowledge areas

| Process group | What went wrong or was skipped |
|---------------|--------------------------------|
| Initiating | A formal project charter was skipped entirely; the sponsor initiated the effort by email without defining business objectives, success criteria, or project manager authority. |
| Planning | Scope and schedule baselines were never created; requirements were added ad-hoc from an informal student survey without impact analysis, technical feasibility spikes, or budget revisions. |
| Executing | Development was executed in isolation without continuous integration or testing against physical payment terminals; code was marked complete without hardware validation. |
| Monitoring and controlling | The team fell into the classic software "invisibility trap," reporting status as "on schedule" based on subjective developer feelings rather than objective, tested software increments. |
| Closing | Formal transition, operational runbooks, user acceptance testing, and cashier training were completely omitted, leading to public failure on launch day and emergency shutdown within 72 hours. |

### Knowledge Areas Most Responsible
1. **Project Scope Management:** Total failure of scope definition and change control. The addition of bus ticketing and parking fees diluted developer attention away from the core payment transaction engine without any formal change requests or schedule adjustments.
2. **Project Quality Management:** Total absence of integration testing and quality assurance. Releasing financial software without executing hardware-in-the-loop tests on physical canteen terminals under simulated peak network conditions directly triggered the 40% failure rate.
3. **Project Stakeholder Management:** Disconnect between project execution and key operational stakeholders. The sponsor was absentee, while canteen staff and students—the primary end users—were never consulted or trained prior to go-live.

## 5. Ethics
- **Decision Examined:** The project leadership's decision to deploy the CampusPay app into live campus-wide production on September 1 despite knowing that no end-to-end integration tests had been conducted with physical point-of-sale card terminals.
- **Responsibility:** The decision breached the ethical standard of responsibility by prioritizing an arbitrary calendar deadline over the fundamental duty of delivering a reliable, safe financial tool. The team abandoned its professional duty of care toward students whose meal access was jeopardized.
- **Respect:** The decision showed deep disrespect toward student diners and frontline canteen workers, forcing cashiers to endure customer frustration, manual ledger disputes, and doubled queues during peak lunch periods.
- **Fairness:** The decision was profoundly unfair to canteen cashiers, who were blindsided by a failing system without training or contingency workflows, unfairly absorbing the blame for IT leadership's negligence.
- **Honesty:** The decision violated honesty by tacitly communicating to university leadership and users that the app was production-ready, actively concealing the glaring absence of hardware integration testing.

## 6. What our project will do differently

| # | Commitment (We will ...) | Measured by | By week | Charter line |
|---|--------------------------|-------------|---------|--------------|
| 1 | We will maintain an approved project charter with a named sponsor who actively evaluates deliverables at formal review gates | Signed charter and documented approval minutes at Week 1 (charter), Week 7 (MVP), and Week 13 (pilot readiness) | 1 | Section 9 (Authority) & Section 10 (Approval) |
| 2 | We will strictly freeze project scope to prevent creep, prioritizing 100% completion of Must features before any Should/Could features | Zero non-Must feature pull requests merged before week 7; 100% of Must features verified in live demo | 7 | Objective O1 & Section 3 (Scope In/Out) |
| 3 | We will validate system performance, concurrency, and latency under simulated peak load before any live pilot | Load test report demonstrating broadcast latency <= 500 ms at 95th percentile under 100 simulated clients | 13 | Objective O3 & Objective O4 |
| 4 | We will execute a controlled live classroom pilot on the real campus network with real students and verified fallback mechanisms | Live pilot conducted with 50 students on campus Wi-Fi with 0 blocking defects and SockJS fallback validated | 14 | Objective O2 & Section 6 (Assumptions) |
| 5 | We will enforce rigorous automated testing and quality gates through continuous integration on every merged code branch | CI pipeline enforcing >= 80% automated line test coverage and zero failing builds across all 10 build phases | 14 | Objective O5 & Section 7 (Constraints) |
