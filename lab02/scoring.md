# Weighted Scoring Analysis · Build vs. Buy vs. Hybrid · Realtime Quiz

Weights (agreed 2026-10-06, before scoring): learning 40, cost 25, time 20, fit 15. Sum = 100.

## Criteria and Weight Rationale (2026-10-06)

- **Learning value for the capstone (Weight: 40):** The primary institutional objective of this course is student mastery of full-stack engineering, real-time protocols, and agile teamwork.
- **Cost within the 200 USD cash budget (Weight: 25):** The 200 USD budget is an absolute hard cap with zero approver for overspend.
- **Time to the week-14 pilot (Weight: 20):** The pilot must execute in week 14 before academic semester marks close; late delivery results in course failure.
- **Fit to the 47 functional requirements (Weight: 15):** The solution must satisfy institutional data sovereignty, room code access, and grading exports.

## Options Description

1. **Build (In-house capstone):** The student team builds the application from scratch using Spring Boot, Vue.js, and WebSockets, hosting on a 25 USD/month Linode VPS (100 USD total) with custom domain (15 USD).
2. **Buy (SaaS):** Subscribe to a commercial quiz platform (Quizizz for Schools / Kahoot! EDU tier) at 39 USD/month for 4 months = 156 USD total.
3. **Hybrid:** Procure a managed real-time communication service (Pusher Channels / Ably) at 29 USD/month for 4 months = 116 USD, and build custom quiz authoring, grading algorithms, and reporting dashboards in-house on a mini VPS (50 USD).

## Scoring Matrix

| Criterion | Weight | Build | Buy (SaaS) | Hybrid |
| --------- | :----: | :---: | :--------: | :----: |
| Learning value for the capstone | 40 | 5 | 1 | 3 |
| Cost within the 200 USD cash budget | 25 | 4 | 3 | 3 |
| Time to the week-14 pilot | 20 | 3 | 5 | 4 |
| Fit to the 47 functional requirements | 15 | 5 | 3 | 4 |
| **Weighted score** | | **435** | **260** | **335** |
| **Percent of maximum (500)** | | **87 %** | **52 %** | **67 %** |

## Score Justifications (Evidence)

- **Learning value:**
  - Build (5): Students implement architecture, WebSocket protocols, security, and automated CI pipelines end-to-end.
  - Buy (1): Zero engineering or coding experience gained; configuration only.
  - Hybrid (3): Practical API integration experience gained, but offloads core concurrency and distributed systems engineering.
- **Cost within 200 USD:**
  - Build (4): 100 USD VPS + 15 USD domain = 115 USD total, leaving an 85 USD reserve buffer.
  - Buy (3): 39 USD/month x 4 = 156 USD (78 % of budget), leaving a tight 44 USD reserve buffer.
  - Hybrid (3): 116 USD SaaS + 50 USD VPS = 166 USD (83 % of budget), leaving a fragile 34 USD reserve buffer.
- **Time to week-14 pilot:**
  - Build (3): 14-week delivery timeline carries implementation risks and testing overhead.
  - Buy (5): Immediate commercial availability; ready within 24 hours.
  - Hybrid (4): Eliminates WebSocket socket server development, saving 48 h of development time.
- **Fit to requirements:**
  - Build (5): 100 % tailored to all 47 functional requirements (FR-A1..FR-N3) and guarantees campus data sovereignty.
  - Buy (3): Proprietary cloud hosting violates campus data isolation; lacks customized grading logic and schema exports.
  - Hybrid (4): Satisfies data storage and custom UI rules, but subject to vendor rate limits and external API schemas.

## Calculations

- **Build:** $40 \times 5 + 25 \times 4 + 20 \times 3 + 15 \times 5 = 200 + 100 + 60 + 75 = 435$ (87 %)
- **Buy:** $40 \times 1 + 25 \times 3 + 20 \times 5 + 15 \times 3 = 40 + 75 + 100 + 45 = 260$ (52 %)
- **Hybrid:** $40 \times 3 + 25 \times 3 + 20 \times 4 + 15 \times 4 = 120 + 75 + 80 + 60 = 335$ (67 %)

## Sensitivity Analysis

Move 10 points of weight from the heaviest criterion (Learning: 40 -> 30) to the lightest criterion (Fit: 15 -> 25):
- Learning value: 30
- Cost within 200 USD: 25
- Time to week-14 pilot: 20
- Fit to requirements: 25
- Sum = $30 + 25 + 20 + 25 = 100$

Recomputed weighted scores:
- **Build:** $30 \times 5 + 25 \times 4 + 20 \times 3 + 25 \times 5 = 150 + 100 + 60 + 125 = 435$ (87 %)
- **Buy:** $30 \times 1 + 25 \times 3 + 20 \times 5 + 25 \times 3 = 30 + 75 + 100 + 75 = 280$ (56 %)
- **Hybrid:** $30 \times 3 + 25 \times 3 + 20 \times 4 + 25 \times 4 = 90 + 75 + 80 + 100 = 345$ (69 %)

**Conclusion:** Winner is unchanged: **Build** remains the highest-scoring option with 435 points (87 %).
