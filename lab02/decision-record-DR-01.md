# DR-01 · Open-day demo scope, week 10

| Field | Value |
| :------- | :------------------------------------------------------ |
| Status | Approved |
| Date | 2026-10-24 |
| Sponsor | Head of the IT department |
| PM | Dr. Alex Vance, Supervising Lecturer |
| Decision | Adopt Counter-proposal 1: Deliver F09 and F10 by week 10 |

---

## 1. Context

At the end of week 4, the sponsor requested that all 5 Should features (110 h total) be demonstrable at the faculty open day in week 10, alongside the planned week-14 pilot.

Governing fixed constraints:
- **C-01:** Week-14 pilot with 50 students remains fixed.
- **C-02:** Team capacity is strictly 40 h/week (240 h total across weeks 5–10).
- **C-03:** Cash budget remains capped at 200 USD with zero additional funds.

Data sheet analysis showed that 152 h of Must work remained for weeks 5–10. Adding all 110 h of Should scope created a total demand of 262 h against 240 h available capacity, resulting in a 22 h deficit and depleting all contingency.

---

## 2. Options Considered

1. **Option 1 · Full Scope by Week 10:** Attempt all Must (152 h) + all Should (110 h) = 262 h. Time impact: 0 weeks; Cost impact: 0 USD; Quality impact: Overtime induces defects; creates high probability of application crash during the public open day demo. Violates capacity constraint C-02.
2. **Option 2 · Counter-Proposal 1 (Selected):** Complete all Must (152 h) + F09 Responsive Design (20 h) + F10 Analytics (30 h) = 202 h by week 10. Time impact: 0 weeks; Cost impact: 0 USD; Quality impact: Fully functional mobile responsive student UI and live instructor analytics dashboard; retains 38 h safety buffer.
3. **Option 3 · Counter-Proposal 2 (Mocked Demo):** Build a mocked-data demo interface (8 h) for week 10; keep all Should features on original schedule for week 14. Time impact: 0 weeks; Cost impact: 0 USD; Quality impact: Visual presentation only, without interactive student participation.

---

## 3. Decision

The sponsor approved **Counter-Proposal 1 (Option 2)**.
- Features **F09 (Responsive design, 20 h)** and **F10 (Analytics and reporting, 30 h)** are scheduled into Sprints 3, 4, and 5 (weeks 5 through 10).
- Features **F11 (CSV/PDF Export, 24 h)**, **F12 (Real-time notifications, 12 h)**, and **F13 (Multimedia, 24 h)** remain assigned to Sprints 6 and 7 (weeks 11 through 13) for the week-14 pilot release.
- All Could features (F14, F15, F16, F17) remain classified as Won't for release 1.0.

---

## 4. Consequences

- **Schedule Baseline:** A new interim milestone `M-06b: Open Day Demo (Must + F09 + F10)` is inserted at the end of week 10.
- **Buffer:** A 38 h buffer ($240\text{ h} - 202\text{ h}$) is preserved across weeks 5–10 to handle unexpected defect remediation.
- **Risk Log:**
  - `R-10:` High concurrent audience Wi-Fi interference during the live auditorium demonstration.
  - `R-11:` Incomplete reporting export (F11) requested by attendees during live presentation.
- **Budget:** 0 USD cash expended.

---

## 5. Approvals

- **Sponsor:** Head of IT Department — Approved (2026-10-24)
- **Project Manager:** Dr. Alex Vance — Approved (2026-10-24)

