# Constraints and assumptions log · Realtime Quiz · v0.1 · week 2

| Id | Type | Statement (measurable) | Source / owner | Validate by |
| ---- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ | ----------- |
| C-01 | Constraint | Live pilot with 50 students must execute in week 14 (deadline: 2026-12-31) before semester grades close. | charter, Milestones / Dean's calendar | fixed |
| C-02 | Constraint | Student engineering effort is strictly capped at 4 developers x 10 h/week = 40 h/week (560 person-hours total). | charter, Resources / Course syllabus | fixed |
| C-03 | Constraint | Cash expenditure cannot exceed 200 USD total across hosting, domain, and development tooling. | charter, Budget / Head of IT | fixed |
| C-04 | Constraint | Target production runtime is restricted to a single virtual server node (2 vCPU, 2 GB RAM, Debian 12, gicitc.com). | charter, section Constraints & Tech Spec | fixed |
| C-05 | Constraint | Student quiz marks and user credentials must reside entirely on departmental servers with zero third-party cloud data transmission. | Departmental Data Sovereignty Policy | fixed |
| A-01 | Assumption | Campus gateway proxy permits WebSocket traffic on port 443 without dropping idle sessions under 60 seconds. | owner: Lead Dev | W3 -> R-01 |
| A-02 | Assumption | Target VPS instance sustains 20 concurrent rooms of 100 participants with WebSocket broadcast latency <= 500 ms at 95th percentile. | owner: Backend Dev | W13 -> R-02 |
| A-03 | Assumption | At least 2 course instructors and 50 registered students attend the scheduled 45-minute live classroom pilot session in week 14. | owner: PM | W11 -> R-03 |
| A-04 | Assumption | Student developer velocity averages >= 18 story points per two-week sprint across Sprints 1 through 7. | owner: PM | W4 -> R-04 |
| A-05 | Assumption | Server-authoritative timing clock maintains synchronization drift <= 200 ms relative to participant browser clocks. | owner: Frontend Dev | W5 -> R-05 |

Review at every milestone. Overdue assumption = open issue.
