# Sprint 1 Planning & Estimation Simulation

Planning Poker records, estimation debate convergence dialogues, and capacity allocation for Sprint 1 (2026-10-20 to 2026-11-02).

## 1. Capacity & Commitment Check

- **Team Size:** 4 student developers (Students A, B, C, D).
- **Weekly Capacity:** 10 hours per student $\times$ 2 weeks = 20 hours per student.
- **Gross Capacity:** 80 person-hours.
- **Scrum Ceremonies Overhead:** Planning (2 h), Daily Scrums (2.5 h), Review (1.5 h), Retrospective (1 h), Refinement (1 h) = 8 h per student $\times$ 4 = 32 hours total (8 hours per person).
- **Net Development Capacity:** $80 - 32 = 48$ hours focus time.
- **Planning Calibration:** At $1\text{ story point} \approx 2.5\text{ focus hours}$, maximum sprint capacity is $\approx 28$ points.
- **Total Points Committed:** 26 story points ($26 \times 2.5 = 65\text{ nominal effort hours}$, fitting well within the 80-hour envelope).

---

## 2. Planning Poker Sizing Log (Fibonacci Scale: 1, 2, 3, 5, 8)

| Item ID | Backlog Item Summary | Dev A | Dev B | Dev C | Dev D | Round 1 Consensus | Final Sizing |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **B-01** | User authentication & role login | 5 | 5 | 8 | 5 | Split (8 vs 5) | **5 pts** |
| **B-02** | Multiple-choice quiz authoring | 3 | 5 | 5 | 5 | Minor divergence | **5 pts** |
| **B-03** | 6-character room code session init | 3 | 3 | 2 | 3 | Immediate consensus | **3 pts** |
| **B-04** | Student lobby join via room code | 3 | 3 | 3 | 3 | Immediate consensus | **3 pts** |
| **B-05** | WebSocket question broadcast | 5 | 8 | 8 | 5 | Split (8 vs 5) | **5 pts** |
| **B-06** | Synchronized question timer | 3 | 3 | 5 | 3 | Minor divergence | **3 pts** |
| **B-07** | Answer submission & ACK | 2 | 2 | 2 | 3 | Immediate consensus | **2 pts** |
| **Total** | | | | | | | **26 pts** |

---

## 3. Convergence Debates (High/Low Discrepancy > 1 Step)

### Debate 1: Item B-01 · User Authentication & Role Login (Dev C voted 8 vs. Devs A, B, D voted 5)
- **Dev C (High - 8):** *"Spring Security 7 has breaking changes around `SecurityFilterChain` and JWT filters compared to Spring Boot 3 tutorials. Configuring JWT signing, token refreshing, and exception handling for invalid tokens will easily blow past 5 points for our first sprint."*
- **Dev A (Low - 5):** *"We do not need token refreshing in Sprint 1. The acceptance criteria only require stateless username/password verification and a basic HMAC-signed JWT containing user roles. In our Phase 1 spike, we already tested the basic auth filter."*
- **Dev B:** *"I agree with A. If we scope out token revocation and blacklist tables for this sprint, a basic Spring Security JWT filter is a standard 5-point task."*
- **Dev C:** *"If we explicitly defer refresh tokens and account lockout to Sprint 3, then 5 points is feasible. I change my vote to 5."*
- **Outcome:** **Unanimous 5 points.**

### Debate 2: Item B-05 · WebSocket Question Broadcast (Devs B, C voted 8 vs. Devs A, D voted 5)
- **Dev B (High - 8):** *"Broadcasting live questions to up to 50 simulated clients requires setting up STOMP over WebSocket with SockJS fallback. If a browser disconnects mid-quiz, handling reconnection without dropping session state is complex."*
- **Dev D (Low - 5):** *"Handling reconnection is part of edge-case hardening in Sprint 2. The Sprint 1 acceptance criteria strictly state: when the instructor clicks display, connected clients receive the payload within 500 ms. The Phase 1 spike verified that Spring's `@MessageMapping` broadcasts in under 80 ms locally."*
- **Dev C:** *"What if SockJS fails through the campus proxy during the live demo?"*
- **Dev A (PO):** *"The proxy configuration was tested in Week 2 spike. For Sprint 1, our acceptance test runs in our local Docker staging environment, not the live campus gateway. Disconnection recovery will be estimated as a separate story in Sprint 2."*
- **Dev B:** *"Understood. Limiting scope strictly to broadcast delivery makes it a solid 5 points."*
- **Outcome:** **Unanimous 5 points.**

