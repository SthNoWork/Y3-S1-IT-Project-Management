# Project profile · Realtime Quiz

References: [project-charter.md](../lab01/project-charter.md) · [moscow.md](../lab02/moscow.md) · [constraints.md](../lab02/constraints.md)

## 1. Selection Criteria Evaluation

| # | Criterion | Adaptive Score (1–5) | Weight ($W$) | Weighted Score ($W \times S$) | Evidence & Citation |
| - | :--- | :---: | :---: | :---: | :--- |
| 1 | Requirements stability | 3 | 20 | 60 | Core Must requirements are locked (8 features, 300 h in [moscow.md](../lab02/moscow.md)), but 5 Should and 4 Could features (204 h / 40.5 % of effort) flex based on pilot feedback and open day requirements ([DR-01](../lab02/decision-record-DR-01.md)). |
| 2 | Technical uncertainty | 4 | 25 | 100 | High architectural uncertainty regarding WebSocket broadcast latency under 500 ms ([project-charter.md](../lab01/project-charter.md) O3) and risk of campus proxy blocking traffic, requiring SockJS fallback and early prototyping ([constraints-assumptions-log.md](../lab02/constraints-assumptions-log.md) A-01). |
| 3 | Team experience with agile | 2 | 15 | 30 | First formal Scrum project for all 4 student developers; Java and Spring Boot learned concurrently, requiring structured templates and prescriptive governance ([lab_03_instructions.md](lab_03_instructions.md) §1). |
| 4 | Contract and governance constraints | 2 | 20 | 40 | Fixed 14-week semester calendar with non-negotiable grading deadlines ([constraints.md](../lab02/constraints.md) C-01), 200 USD cash ceiling (C-03), and academic PM oversight requiring predefined phase gates. |
| 5 | Need for early delivery and feedback | 5 | 20 | 100 | Early working software is mandatory for the Week 7 MVP checkpoint ([project-charter.md](../lab01/project-charter.md) M-05) and Week 10 faculty open day demonstration ([DR-01](../lab02/decision-record-DR-01.md)) well before the Week 14 pilot. |
| – | *Sponsor availability* | 3 | – *(unweighted)* | – | Sponsor (Head of IT) commits to bi-weekly milestone checkpoints and Sprint Reviews, but cannot attend daily operational team meetings. |
| **Total** | | | **100** | **330** | |

$$\text{Profile Index} = \frac{\sum (W \times S)}{100} = \frac{330}{100} = 3.30$$

### Interpretation Bands
- $< 2.5$: Predictive (Waterfall)
- **$2.5$ – $3.5$: Hybrid (Score: 3.30)**
- $> 3.5$: Agile (Pure Scrum)

---

## 2. Profile Summary

Realtime Quiz is a fixed-deadline educational software initiative characterized by high technical uncertainty and stringent academic governance. The profile is heavily driven by two dominant factors: severe technical uncertainty surrounding real-time WebSocket concurrency (Weight: 25, Score: 4) and an essential requirement for early, iterative stakeholder feedback (Weight: 20, Score: 5) prior to the week-14 pilot. Therefore, Task 2 must systematically evaluate **Waterfall**, **Pure Scrum**, and a tailored **Hybrid** approach to determine how best to reconcile rigid calendar gates with rapid sprint-based technical learning.

