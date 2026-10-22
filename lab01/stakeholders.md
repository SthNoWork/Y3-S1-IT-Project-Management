# Initial Stakeholder Analysis: Realtime Quiz Platform

## 1. Priority Stakeholders (High Influence, High Interest)
The two stakeholders with the highest influence and highest interest are **S01 (Head of the IT department / Sponsor)** and **S02 (Project Manager / Supervising Lecturer)**. They demand the project manager's immediate and primary attention because S01 controls the funding, authorizes project scope changes, and establishes the strategic mandate for departmental innovation, while S02 directly coordinates the daily work, ensures pedagogical rigor, and removes blockers for the student engineering team. Maintaining active alignment between S01 and S02 ensures that the project remains protected from scope creep, stays within the 200 USD cash cap and 490-hour effort budget, and reliably progresses through the week 7 MVP demonstration and week 14 classroom pilot.

## 2. Veto Stakeholder
The primary "veto" stakeholder for this project is **S08 (Data Protection Officer)**. Although S08 has low day-to-day operational interest (categorized as High Influence, Low Interest), institutional compliance regulations dictate that no software system can collect student names, identifiers, or assessment grades without formal privacy sign-off. If S08 does not receive and approve the one-page data description and retention procedure prior to week 14, the live classroom pilot cannot legally take place, effectively stopping the project at the final gate regardless of technical readiness.

## 3. Power / Interest Grid Summary

| Stakeholder ID | Stakeholder Name / Group | Quadrant | Strategy |
|----------------|--------------------------|----------|----------|
| S01 | Head of the IT department | High Influence / High Interest | Manage Closely (Weekly dashboards, phase gates at week 1, 7, 13) |
| S02 | Project Manager (Supervising Lecturer) | High Influence / High Interest | Manage Closely (Daily direction, code review, continuous steering) |
| S08 | Data Protection Officer | High Influence / Low Interest | Keep Satisfied (Deliver 1-page privacy architecture before week 12) |
| S03 | Student development team (4) | Medium Influence / High Interest | Keep Informed & Empowered (Weekly sprints, clear task boards) |
| S05 | Course instructors | Medium Influence / High Interest | Keep Informed & Consulted (UI feedback during Phase 3 & 6) |
| S06 | IT operations (VPS admin) | Medium Influence / Medium Interest | Keep Satisfied (Production checklist & runbook by week 12) |
| S07 | Campus network administrator | Medium Influence / Low Interest | Keep Satisfied (Validate SockJS fallback to avoid proxy issues) |
| S09 | Software engineering lecturer | Medium Influence / Medium Interest | Keep Satisfied (Verify 80% CI test coverage standards) |
| S04 | Pilot students (50) | Low Influence / Medium Interest | Keep Informed (Clear onboarding and briefing in week 14) |
| S10 | Commercial Quiz SaaS vendor | Low Influence / Low Interest | Monitor (Benchmark pricing and features for contingency review) |

See [stakeholders.csv](stakeholders.csv) for the complete tabular stakeholder register.
