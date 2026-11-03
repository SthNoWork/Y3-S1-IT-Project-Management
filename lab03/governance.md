# Project governance · Realtime Quiz

Governance framework defining phase gates, numerical tolerance boundaries, exception escalation paths, status reporting, and project closure criteria.

## 1. Stage Gates ($G1$ to $G4$)

### Gate $G1$ · Plan & Architecture Approval (Week 3 · 2026-10-19)
- **Inputs:** Project Charter v1.0, MoSCoW Scope Baseline (504 h), System Architecture Diagram, WebSocket SockJS Spike Benchmark Report, Sprint 1 Backlog.
- **Decision Maker:** Project Manager (Dr. Alex Vance) and Sponsor (Head of IT).
- **Allowed Outcomes:** `continue`, `continue with changes`, `stop`.
- **Exit Checklist Criteria:**
  - [ ] Project charter signed off with agreed 200 USD budget ceiling and 14-week timeline.
  - [ ] 8 Must features (300 h) fully baselined with traceable functional requirement IDs.
  - [ ] Technical spike validates SockJS fallback over campus port 443 with broadcast latency $\le 500\text{ ms}$.
  - [ ] Linode VPS (2 vCPU / 2 GB RAM) provisioned with automated deployment scripts.
  - [ ] Sprint 1 backlog populated with 7 items satisfying all 5 Definition of Ready criteria.

### Gate $G2$ · MVP Checkpoint Demo (Week 7 · 2026-11-16)
- **Inputs:** Working software build (Sprint 1 + Sprint 2), Automated Test Report, Sprint Burndown data, Tolerance Status.
- **Decision Maker:** Project Manager and Sponsor.
- **Allowed Outcomes:** `continue`, `continue with changes`, `repeat`, `stop`.
- **Exit Checklist Criteria:**
  - [ ] Live end-to-end demonstration of core quiz authoring, live participation, instant scoring, and leaderboard with 0 blocking defects.
  - [ ] Automated line test coverage $\ge 80\,\%$ with 100 % green CI build status on `develop`.
  - [ ] WebSocket broadcast latency benchmarked $\le 500\text{ ms}$ across 50 concurrent local simulated clients.
  - [ ] Planned student effort variance within $\pm 10\,\%$ of the 280-hour mid-term threshold.
  - [ ] Retrospective improvements from Sprints 1 and 2 formally documented and adopted.

### Gate $G3$ · Feature Complete Checkpoint (Week 11 · 2026-12-14)
- **Inputs:** Release Candidate v0.9 deployed to staging VPS, Open Day Demonstration Report (DR-01), Load Test Metrics, Hardening Plan.
- **Decision Maker:** Project Manager and Sponsor.
- **Allowed Outcomes:** `continue`, `continue with changes`, `repeat`.
- **Exit Checklist Criteria:**
  - [ ] 100 % of the 8 Must features and prioritized Should features (F09, F10) deployed and operational on staging VPS.
  - [ ] Faculty Open Day demonstration executed successfully with 0 system crashes.
  - [ ] Load test verifies single-node VPS sustains 20 concurrent rooms of 100 participants with timer drift $\le 200\text{ ms}$.
  - [ ] Static security audit resolves all high/critical vulnerabilities with zero outstanding CVEs.
  - [ ] Contingency reserve has $\ge 40$ person-hours remaining for release hardening.

### Gate $G4$ · Pilot Acceptance & Handover (Week 14 · 2027-01-04)
- **Inputs:** 50-Student Live Pilot Results Log, Deployment Runbook, Production VPS Credentials, Git Repository Master, Sponsor Handover Sign-off.
- **Decision Maker:** Sponsor (Head of IT).
- **Allowed Outcomes:** `continue` (close project), `repeat` (re-run pilot).
- **Exit Checklist Criteria:**
  - [ ] Live classroom pilot executed with $\ge 50$ real student participants completing a 20-question quiz with 0 blocking defects.
  - [ ] Operational runbook complete with step-by-step VPS recovery, backup procedures, and Docker instructions.
  - [ ] Production Git repository handed over with tag `v1.0.0` and clean CI badge.
  - [ ] Total cash expenditure audited and reconciled $\le 200\text{ USD}$ (actual receipts filed).
  - [ ] Formal sponsor acceptance certificate signed and archived.

---

## 2. Numerical Tolerances Matrix

Tolerances establish variance thresholds that the Project Manager can absorb without sponsor escalation. All entries carry explicit numbers or percentages.

| Constraint Area | Stage 1 (W1–3): Inception & Plan | Stage 2 (W4–7): MVP Delivery | Stage 3 (W8–11): Feature Complete | Stage 4 (W12–14): Release & Pilot |
| :--- | :--- | :--- | :--- | :--- |
| **Time (Schedule)** | $\pm 0$ days on Gate $G1$ date | $+3$ calendar days on $G2$ demo | $+3$ calendar days on $G3$ | $\pm 0$ days on Week 14 pilot |
| **Cost (Effort hours)** | $\pm 12$ person-hours ($\pm 10\,\%$) | $\pm 16$ person-hours ($\pm 10\,\%$) | $\pm 16$ person-hours ($\pm 10\,\%$) | $\pm 12$ person-hours ($\pm 10\,\%$) |
| **Cash Budget (USD)** | $+0\text{ USD}$ over $65\text{ USD}$ | $+10\text{ USD}$ over $115\text{ USD}$ | $+10\text{ USD}$ over $165\text{ USD}$ | $+0\text{ USD}$ over $200\text{ USD}$ total |
| **Scope Variance** | $0$ Must scope changes | $\le 12$ h Should scope deferred | $\le 24$ h Should scope deferred | $0$ Must / Should scope changes |
| **Quality (Defects)** | $0$ unresolved architecture blockers | $0$ blocker, $\le 3$ minor bugs | $0$ blocker, $\le 2$ minor bugs | $0$ blocker, $0$ critical, $\le 1$ minor |
| **Risk (Contingency)** | $\ge 50$ h contingency intact | $\ge 45$ h contingency intact | $\ge 30$ h contingency intact | $\ge 15$ h contingency intact |

---

## 3. Escalation & Exception Path

When any operational metric breaches the agreed tolerance boundaries, an exception is immediately escalated along the governance chain:

$$\text{Developers} \longrightarrow \text{Scrum Master} \longrightarrow \text{Project Manager} \longrightarrow \text{Project Sponsor}$$

1. **Trigger:** A developer or SM detects that a sprint forecast breaches time ($> 3$ days), effort ($> 10\,\%$), or quality floors (coverage $< 80\,\%$).
2. **SM Notification:** Within 24 hours, the Scrum Master logs an Exception Warning to the Project Manager.
3. **PM Assessment:** The PM evaluates whether the deviation can be resolved using local sprint re-planning within 48 hours.
4. **Sponsor Exception Report:** If the breach impacts fixed constraints (Gate dates, cash ceiling, or Must scope), the PM delivers a 3-line Exception Report to the Sponsor within 2 business days.

### Three-Line Exception Report Template
```text
1. CAUSE: [State the exact root cause and metric that breached tolerance, e.g., Sprint 2 velocity dropped 8 pts due to Spring Security 7 CVE].
2. IMPACT: [State concrete impact on cost, milestones, and scope, e.g., Gate G2 demo delayed by 4 days, exhausting 16 h contingency].
3. ACTION: [Present recommendation for sponsor approval, e.g., Defer F12 Notifications (12 h) to maintain the fixed Week 7 MVP demo].
```

---

## 4. Progress Reporting Structure

The Project Manager compiles a weekly **Highlight Report** reviewing tolerance metrics:
- **Done:** Completed stories and verified increments against the Sprint Goal.
- **Next:** Prioritized sprint backlog items scheduled for the coming week.
- **Risks & Blockers:** Active risks, open impediments, and contingency burn rate.
- **Tolerance Status:** Green (within limits), Amber (within 80 % of tolerance), Red (breached; exception report issued).

---

## 5. Project Closure Criteria

| Closure Area | Acceptance Criterion | Verified By | Owner |
| :--- | :--- | :--- | :--- |
| **Deliverable Acceptance** | 50-student live pilot executed with 100 % of Must features working and 0 blocking defects. | Sponsor & PM | Product Owner |
| **Technical Handover** | Git repository tagged `v1.0.0` with clean CI, unit test suite, and architectural schema. | Project Manager | Scrum Master |
| **Infrastructure Handover** | Linode production VPS root access, SSH keys, Docker runbooks, and domain DNS transferred to department. | IT Department Admin | Lead Developer |
| **Documentation Handover** | End-to-end operational runbook, disaster recovery manual, and user guide delivered as Markdown in `/docs`. | Course Lecturer | Lead Developer |
| **Lessons Learned** | Consolidated retrospective register from Sprints 1–4 and closure workshop summary archived. | Project Manager | Scrum Master |
| **Administrative Closure** | Cash ledger verified ($\le 200\text{ USD}$), student grades finalized, and project completion certificate signed. | Sponsor | Project Manager |

