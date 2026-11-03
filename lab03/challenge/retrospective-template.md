# Sprint 1 Retrospective Report · Realtime Quiz

**Date:** 2026-11-02 · **Sprint:** 1 · **Attendees:** Students A (PO), B (SM), C (Dev), D (Dev) · **Facilitator:** Student B

---

## 1. Quantitative Sprint Performance & Burndown Analysis

| Metric | Target / Planned | Actual Achieved | Variance |
| :--- | :---: | :---: | :---: |
| **Committed Story Points** | 26 pts (7 items) | 23 pts (6 items) | $-3\text{ pts}$ (88.5 % completion) |
| **Delivered Velocity** | 26 pts | **23 pts** | $-3\text{ pts}$ |
| **Team Hours Logged** | 80.0 h | 78.5 h | $-1.5\text{ h}$ |
| **Automated Test Coverage** | $\ge 80\,\%$ | **83.4 %** | $+3.4\,\%$ (DoD compliant) |
| **Critical Defects in Staging** | 0 | 0 | Met |

### Burndown Diagnostic
- **Bottleneck Identified:** The team fell **2 days behind schedule at Day 5** (18 story points remaining vs. the ideal target of 13.0 points; actual progress on Day 5 corresponded to the Day 3 ideal benchmark).
- **Root Cause of Lag:** Items B-01 and B-05 encountered unexpected complexity with STOMP message broker configuration in Spring Boot and Docker network bridge routing, freezing progress between Days 3 and 6.
- **Unfinished Item Returning to Backlog:** **B-06 (Synchronized question countdown timer, 3 points)** did not satisfy the Definition of Done due to a client-side drift bug (> 350 ms discrepancy under load). It has been returned to the Product Backlog for re-estimation in Sprint 2.
- **Updated Forecast for Sprints 2–4:**
  - Total core Must scope: 120 story points ($300\text{ h} / 2.5\text{ h/pt}$).
  - Remaining Must work: $120\text{ pts} - 23\text{ pts (achieved)} = \mathbf{97\text{ points}}$ across Sprints 2, 3, and 4.
  - Required velocity to finish all Must items: $\approx 32.3\text{ points/sprint}$. Because baseline velocity is 23 points, the team must prioritize strict Must items and defer secondary Should features (F11, F12, F13) to prevent milestone slippage.

---

## 2. Qualitative Feedback

### What Went Well (Positive Takeaways)
1. **WebSocket Infrastructure Proven:** Real-time bi-directional communication between teacher orchestrator and student clients achieved latency under 120 ms locally, thoroughly retiring the project's highest technical risk.
2. **Clean Automated CI Pipeline:** Automated GitHub Actions workflow caught 4 broken regression tests and prevented non-compliant PR merges before reaching `develop`.
3. **High Team Morale:** Daily standups remained strictly within 15 minutes, ensuring blockers were escalated immediately without stalling work.

### What Could Be Improved (Problem Areas)
1. **Late Verification of Sub-System Integration:** Frontend timer components were integrated with backend WebSockets on Day 9, leaving zero time to fix synchronization drift before Sprint Review.
2. **Over-Optimistic Docker Local Environment:** Differences between local Windows development environments and Docker containerized networking caused 8 wasted developer hours during early sprint days.

---

## 3. Actionable Process Improvements for Sprint 2

| # | Action Item | Root Cause Addressed | Owner | Verification Mechanism |
| - | :--- | :--- | :---: | :--- |
| **A-1** | **Enforce Mid-Sprint Integration Checkpoint (Day 5):** All API and WebSocket contracts must have mocked integration tests passing by the end of Day 5. | Eliminates end-of-sprint integration panics (like B-06). | Student B (SM) | Verified at Day 5 Daily Scrum via mock integration test suite. |
| **A-2** | **Standardize Docker Compose Dev Containers:** Mandate that all developers run the identical unified Docker Compose environment locally from Day 1. | Eliminates environment configuration mismatches and wasted debugging hours. | Student C (Dev) | Clean startup script validated in Sprint 2 Planning. |

