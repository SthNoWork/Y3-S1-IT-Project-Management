# Approach comparison · Realtime Quiz

Comparative analysis of candidate life cycle models for the Realtime Quiz project: Predictive (Waterfall), Adaptive (Pure Scrum), and Hybrid (Tailored).

## 1. Candidate Comparison Matrix

| Dimension | Waterfall (Predictive) | Pure Scrum (Adaptive) | Hybrid (Tailored Model) |
| :--- | :--- | :--- | :--- |
| **Requirements handling** | Frozen specification after Week 3; changes routed through formal change board with contract renegotiation. | Emergent Product Backlog; prioritized dynamically by Product Owner at every 2-week sprint boundary. | Fixed Must core (300 h) locked in Phase 1; Should/Could scope (204 h) dynamically selected in 2-week sprints. |
| **Sponsor control (governance)** | High stage-gate control at formal milestone handovers (W3, W8, W13); zero visibility into running software between gates. | Low contractual control; sponsor invited to sprint reviews as attendee, but holds no formal interim approval gates. | High stage-gate control via 4 formal phase gates ($G1$–$G4$) combined with direct bi-weekly sprint review inspections. |
| **First playable quiz (Week)** | **Week 13** (System Integration Phase, leaving 1 week before pilot). | **Week 5** (End of Sprint 1 working increment). | **Week 5** (End of Sprint 1 working increment). |
| **Two primary risks** | 1. Late discovery of WebSocket network/proxy blockers in Week 13 with no time left to remediate.<br>2. Severe inability to adapt to external calendar cuts (e.g., CR-03). | 1. Inexperienced student team drifts without architectural baseline, missing the fixed Week 14 pilot.<br>2. Dual PO/Developer student role leads to unmanaged scope bloat. | 1. Administrative overhead of dual reporting (Scrum ceremonies + stage-gate documentation).<br>2. Friction between sprint timeboxes and rigid stage-gate deadlines. |
| **Profile fit (1–5)** | **2** (Poor: Violates high technical uncertainty and need for early feedback). | **3** (Moderate: Meets technical discovery, but fails strict academic governance). | **5** (Excellent: Blends predictive stage-gate governance with iterative technical sprints). |

---

## 2. Weighted Scoring Summary

Detailed data available in [approach-scoring.csv](approach-scoring.csv).

| Criterion | Weight ($W$) | Waterfall ($S_W$) | Scrum ($S_S$) | Hybrid ($S_H$) |
| :--- | :---: | :---: | :---: | :---: |
| Requirements stability | 20 | 3 (60) | 4 (80) | 5 (100) |
| Technical uncertainty | 25 | 1 (25) | 5 (125) | 4 (100) |
| Team experience with agile | 15 | 3 (45) | 2 (30) | 4 (60) |
| Contract and governance constraints | 20 | 5 (100) | 2 (40) | 5 (100) |
| Need for early delivery and feedback | 20 | 1 (20) | 5 (100) | 5 (100) |
| **Weighted Total** | **100** | **250** | **375** | **460** |

$$\text{Waterfall} = 20(3) + 25(1) + 15(3) + 20(5) + 20(1) = 250$$
$$\text{Pure Scrum} = 20(4) + 25(5) + 15(2) + 20(2) + 20(5) = 375$$
$$\text{Hybrid} = 20(5) + 25(4) + 15(4) + 20(5) + 20(5) = 460$$

---

## 3. Sensitivity Analysis

### Sensitivity Test 1: Decrease Technical Uncertainty by 10, Increase Governance by 10
To evaluate stability if technical uncertainty was overestimated, weight for *Technical uncertainty* is shifted from 25 to 15, and *Contract and governance constraints* is shifted from 20 to 30:
- **Waterfall:** $20(3) + 15(1) + 15(3) + 30(5) + 20(1) = 60 + 15 + 45 + 150 + 20 = 290$
- **Pure Scrum:** $20(4) + 15(5) + 15(2) + 30(2) + 20(5) = 80 + 75 + 30 + 60 + 100 = 345$
- **Hybrid:** $20(5) + 15(4) + 15(4) + 30(5) + 20(5) = 100 + 60 + 60 + 150 + 100 = 470$
- **Result:** Hybrid (470) > Pure Scrum (345) > Waterfall (290). **Ranking unchanged.**

### Sensitivity Test 2: Increase Technical Uncertainty by 10, Decrease Team Experience by 10
To test an extreme agile bias where architectural risks dominate and team experience is discounted, *Technical uncertainty* is shifted from 25 to 35, and *Team experience with agile* is shifted from 15 to 5:
- **Waterfall:** $20(3) + 35(1) + 5(3) + 20(5) + 20(1) = 60 + 35 + 15 + 100 + 20 = 230$
- **Pure Scrum:** $20(4) + 35(5) + 5(2) + 20(2) + 20(5) = 80 + 175 + 10 + 40 + 100 = 405$
- **Hybrid:** $20(5) + 35(4) + 5(4) + 20(5) + 20(5) = 100 + 140 + 20 + 100 + 100 = 460$
- **Result:** Hybrid (460) > Pure Scrum (405) > Waterfall (230). **Ranking unchanged.**

---

## 4. Recommendation

- **Selected Winner:** **Hybrid Model (Weighted Score: 460)**
- **Runner-Up:** **Pure Scrum (Weighted Score: 375)**

The **Hybrid approach** is overwhelmingly recommended because it provides the iterative development speed required to de-risk WebSocket communication by Week 5 while honoring the rigid academic phase gates ($G1$–$G4$) and fixed calendar constraints.

**Switching Condition:**  
Pure Scrum would be selected instead if and only if the departmental sponsor waived all formal interim stage-gate approvals ($G1$–$G4$), removed the external PM's contractual authority, and granted the student Scrum team complete self-directed autonomy over the scope baseline and delivery timeline.

