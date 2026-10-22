# Project charter: Realtime Quiz platform

| Field | Value |
|----------|------------------------------------|
| Version | 1.0 (draft for sponsor approval) |
| Date | 2026-09-29 |
| Sponsor | Head of the IT department |
| PM | Dr. Alex Vance, Supervising Lecturer |

## 1. Purpose and justification
Instructors currently spend substantial uncompensated hours manually marking paper quizzes, while students receive feedback too late to guide active learning during lectures. The Realtime Quiz platform is a dedicated web application enabling instructors to author multiple-choice quizzes and facilitate live, synchronized classroom quiz sessions. Students join quickly using 6-character room codes and compete against a countdown timer with instant scoring, real-time leaderboard rankings, and immediate answer explanations. This project eliminates recurring commercial software licensing fees, preserves absolute institutional ownership of student grading data on campus infrastructure, and automates lecture assessment workflows. See [business-case.md](business-case.md) for the detailed financial justification, cost-benefit analysis, and payback model.

## 2. Objectives and success criteria

| # | Objective (what will be true) | Success criterion (number + week) |
|---|------------------------------------|-----------------------------------|
| O1 | Deploy and demonstrate the core Minimum Viable Product (Must features) | 100% of Must features functional with 0 blocking defects in live demo, week 7 |
| O2 | Conduct a live classroom pilot with end users | 50 student participants in 1 live quiz session with 0 blocking defects, week 14 |
| O3 | Maintain high-responsiveness real-time broadcast latency | <= 500 ms WebSocket broadcast latency at 95th percentile under 100 simulated clients, week 13 |
| O4 | Demonstrate single-node concurrent capacity and server timer precision | 20 concurrent sessions of 100 participants on 2 vCPU and 2 GB RAM with timer drift <= 200 ms, week 13 |
| O5 | Achieve rigorous automated testing and continuous integration health | >= 80% automated line test coverage with green CI status on 100% of merged pull requests, week 14 |

## 3. High-level scope

In scope:
- Web-based quiz authoring interface with multiple-choice questions and timer configuration
- Live session orchestration engine with 6-character room codes and instructor session controls
- Real-time participant interaction engine with instant scoring, timer display, and live leaderboards
- Role-based user authentication and security module for instructors, students, and guests
- Session performance analytics dashboard with downloadable CSV and PDF student result reports
- Production deployment package with operational runbooks and Docker configuration

Out of scope:
- Native mobile applications for iOS and Android
- Question types other than multiple choice (such as free-text or essay answers)
- Integrated video conferencing or live audio streaming
- Direct Learning Management System (LMS) integration or LTI protocol connectivity
- Multi-node distributed clustering and multi-server scaling architecture

## 4. Milestones

| Week | Milestone | Ends process group |
|------|------------------------------------|--------------------|
| 1 | Charter approved, team formed | Initiating |
| 3 | Requirements baseline, system architecture, and UI wireframes | Planning |
| 5 | Phase 3-4: Live session core and question timer operational | Executing |
| 7 | Phase 5: MVP demo (scoring, leaderboard, core Must features) | Executing |
| 10 | Phase 6-7: Analytics, CSV/PDF export, notifications, and media | Executing |
| 13 | Phase 8-9: Load testing (100 users), hardening, operations runbook ready | Monitoring and controlling |
| 14 | Phase 10: Pilot with 50 students, project closure and handover | Closing |

## 5. Budget summary

Effort: students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h
Cash: hosting 4 x 25 USD = 100 USD; domain 15 USD; tools 60 USD; reserve 25 USD (14 %); total 200 USD

## 6. Assumptions
- Linode VPS (2 vCPU, 2 GB RAM) and gicitc.com host network infrastructure remain available and stable throughout the 14-week project.
- The campus proxy server allows WebSocket traffic or reliably permits transparent fallback to SockJS without dropping participant connections.
- The four student developers commit 8 hours per week each across the 14 weeks and possess foundational proficiency in Java and web development.
- Departmental course instructors and at least 50 enrolled students agree to participate in the scheduled live pilot session in week 14.

## 7. Constraints
- Time: Fixed schedule of 14 weeks starting 2026-09-29 and ending 2026-12-31, with strict milestone deadlines for the week 7 MVP demo and week 14 pilot.
- Cash: Strict financial ceiling of 200 USD cash covering all hosting, domain registration, tooling, and contingency reserve.
- Effort: Strict ceiling of 490 person-hours total (4 students at 8 h/week and 1 supervising lecturer as PM at 3 h/week).
- Infrastructure: Deployment constrained to a single-node virtual private server with 2 vCPU and 2 GB RAM (no multi-node clustering).

## 8. High-level risks
- Campus proxy blocking WebSocket connections: Fallback to SockJS emulation transport configured during core real-time development.
- Modern framework volatility (Spring Boot 4 and Spring Security 7): Early architectural spikes and security setup executed in Phase 1-2.
- Client-server clock drift causing answer submission race conditions: Enforce authoritative server-side timing and a 200 ms grace tolerance window.
- Khmer script rendering failures in PDF export: Embed UTF-8 Khmer fonts and validate export during Phase 6.
- Scope creep from Could features (chat, question bank) encroaching on the MVP: Strict PM scope enforcement and change control.

## 9. Project manager authority
The Project Manager is authorized to allocate and reassign team tasks, select development tools, re-plan student effort within the 490-hour total, and authorize cash expenditures from the 25 USD contingency reserve without prior sponsor approval. Any adjustments that modify defined scope boundaries, reschedule external milestone commitments (specifically the week 7 MVP demo or the week 14 pilot), or exceed the 200 USD cash budget require formal written approval from the Sponsor within 5 working days.

## 10. Approval
Sponsor: ____________________ Date: 2026-09-29
PM: ____________________ Date: 2026-09-29
