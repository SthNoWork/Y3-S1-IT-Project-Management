# Lab-03 · Life Cycle Selection and Tailoring Decision Record

The Realtime Quiz project adopts a **Tailored Hybrid life cycle model** (scoring 460 / 500 in multi-criteria analysis) that strategically bridges predictive governance and agile delivery. Under this model, Weeks 1–3 focus on predictive inception, architectural spikes, and baseline scope locking; Weeks 4–11 execute four timeboxed 14-day Scrum sprints to iteratively de-risk real-time WebSocket communication; and Weeks 12–14 execute release hardening, load testing, and the live 50-student pilot. This approach guarantees that the non-negotiable 14-week academic calendar and 200 USD budget ceilings are preserved while granting student developers the iterative velocity necessary to solve technical uncertainties.

Governance is maintained through four formal stage gates ($G1$ to $G4$) aligned with critical academic milestones: Plan Approval (Week 3), MVP Checkpoint (Week 7), Feature Complete (Week 11), and Pilot Acceptance (Week 14). A quantitative tolerance matrix provides pre-authorized operational boundaries for schedule, effort, cash, and quality, enabling the student team to resolve local variances without bureaucracy. Deviations exceeding these tolerances trigger an immediate 4-step escalation chain (`Devs -> SM -> PM -> Sponsor`) via a standardized three-line exception report, ensuring total transparency with zero sponsor surprise.

## Deliverables Directory

| File | Description |
| :--- | :---------- |
| lab03/project-profile.md | Characterisation of project across 5 criteria yielding a hybrid profile score of 3.30. |
| lab03/approach-comparison.md | Comparative evaluation of Waterfall, Pure Scrum, and Hybrid with sensitivity analyses and recommendation. |
| lab03/approach-scoring.csv | Weighted scoring matrix calculating weighted totals (Waterfall: 250, Scrum: 375, Hybrid: 460). |
| lab03/tailoring-decision-record.md | Architectural Decision Record (TDR-01) documenting context, decision, consequences, tailoring, and phase gates. |
| lab03/life-cycle.mmd | Mermaid Gantt chart spanning 14 weeks with 4 equal 14-day sprints and 4 phase-gate milestones ($G1$–$G4$). |
| lab03/life-cycle.svg | Scalable vector graphic export of the 14-week hybrid life cycle Gantt chart. |
| lab03/scrum-setup.md | Scrum framework configuration defining roles, Sprint 1 goal, event calendar, 5-point DoR, and 9-point DoD. |
| lab03/sprint-1-backlog.csv | Sprint 1 backlog containing 7 Must user stories ($\le 8$ points each, 26 points total) in Given/When/Then format. |
| lab03/governance.md | Phase gates $G1$–$G4$ exit checklists, numerical tolerances matrix, exception escalation path, and closure criteria. |
| lab03/README.md | Master lab manifest, approach summary, reused inputs index, and version change log. |
| lab03/challenge/sprint-1-planning.md | Extra Credit: Planning Poker simulation and debate convergence dialogue for stories B-01 to B-07. |
| lab03/challenge/burndown.mmd | Extra Credit: Mermaid xychart-beta Sprint 1 ideal vs. actual burndown chart with variance analysis. |
| lab03/challenge/retrospective-template.md | Extra Credit: Sprint 1 retrospective report with empirical metrics and 2 actionable process improvements. |
| lab03/challenge/prince2-comparison.md | Extra Credit: Mapping matrix of 10 hybrid concepts to PRINCE2 7 equivalents and comparative essays. |

## Inputs Reused from Earlier Labs

| Input File | Source Lab | Content & Assets Reused |
| :--- | :---: | :--- |
| `lab01/project-charter.md` | Lab 01 | Project purpose, 14-week milestone schedule ($G1$, $G2$, $G4$), 200 USD budget ceiling, and quality objectives O1–O5. |
| `lab01/stakeholders.md` | Lab 01 | Sponsor (Head of IT), PM (Supervising Lecturer), and student development team profiles. |
| `lab02/moscow.md` | Lab 02 | MoSCoW rating breakdown (8 Must / 300 h, 5 Should / 110 h, 2 Could / 42 h, 2 Won't / 52 h; 504 h total). |
| `lab02/constraints.md` | Lab 02 | Locked time driver (C-01), locked cost ceiling (C-03), and quality floor benchmarks (latency $\le 500\text{ ms}$). |
| `lab02/decision-record-DR-01.md` | Lab 02 | Week 10 faculty Open Day demonstration milestone and feature scope inclusion (F09, F10). |

## Change Log

| Date | Version | Author | Change Summary |
| :---: | :---: | :---: | :--- |
| 2026-10-06 | 0.1 | PM & Scrum Team | Lab-03: Life cycle selection, Scrum setup, and governance framework added. |
