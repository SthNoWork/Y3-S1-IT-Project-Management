# Business case: live quizzes for the IT department

## 1. Problem
Instructors across the IT department currently rely on paper-based quizzes or rudimentary static forms to conduct classroom assessments. This approach generates significant administrative marking overhead, delays pedagogical feedback to students until subsequent weeks, and offers no real-time visibility into student comprehension during lectures.

Assumptions:
- Lecturers running weekly quizzes: 10
- Manual marking and collation time per lecturer per week: 1 h
- Teaching weeks per academic year: 30
- Total instructor hours lost annually: 10 lecturers x 1 h/week x 30 weeks = 300 hours
- Notional value of one hour of faculty/assistant time: 10 USD (used as a conservative benchmark to compare internal effort with commercial alternatives)
- Baseline annual cost of manual grading: 300 h x 10 USD/h = 3,000 USD/year

## 2. Options

| Option | Description | One-off cost | Annual cost | Annual benefit |
|--------|-------------|--------------|-------------|----------------|
| A | Do nothing (continue manual marking on paper/forms) | 0 USD | 0 USD | 0 USD |
| B | Buy commercial Quiz SaaS (Kahoot! EDU / Wooclap) | 0 USD | 1,800 USD | 3,000 USD |
| C | Build Realtime Quiz (internal student capstone build) | 4,900 USD | 300 USD | 4,800 USD |

### Option Details
- **Option A (Do nothing):** Maintain current manual grading practices. There are zero new expenditures, but the department continues to lose 3,000 USD equivalent in productive faculty time each year, while students receive no interactive real-time classroom feedback.
- **Option B (Buy SaaS):** Procure a commercial cloud-based interactive quiz subscription for 10 instructors. Research citation: Educational institution pricing for Kahoot! EDU Pro is 14.99 USD (~15 USD) per teacher/month billed annually (source: [kahoot.com/schools/plans-pricing](https://kahoot.com/schools/plans-pricing/), accessed September 2026). Total annual software subscription cost: 10 lecturers x 15 USD/month x 12 months = 1,800 USD/year. One-off setup is negligible (0 USD). Annual benefit is 3,000 USD in saved marking time.
- **Option C (Build Realtime Quiz):** Construct a specialized, server-authoritative live quiz platform within the department using a 4-student capstone team supervised by a lecturer over 14 weeks. One-off development effort is 490 person-hours valued at 10 USD/h = 4,900 USD (actual out-of-pocket cash required is capped at 200 USD by the project charter). Ongoing annual operational cost is Linode VPS hosting: 12 months x 25 USD/month = 300 USD/year. Annual benefit comprises 3,000 USD in saved grading time plus 1,800 USD in avoided recurring commercial SaaS licensing fees, totaling 4,800 USD/year.

## 3. Comparison

| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
|--------|--------------------|-----------------|----------------------------|
| B | 3,000 - 1,800 = 1,200 USD | 0 (no one-off) | 1,800 - 1,080 = 720 USD |
| C | 3,000 + 1,800 - 300 = 4,500 USD | 4,900 / 4,500 = 1.1 years | 2,580 USD net benefit; payback = 1.9 years |

### Calculation & Sensitivity Notes
- **Option B Net Benefit:** 3,000 USD benefit - 1,800 USD subscription = 1,200 USD/year.
- **Option C Net Benefit:** 4,800 USD total benefit (3,000 USD marking saved + 1,800 USD SaaS avoided) - 300 USD hosting = 4,500 USD/year.
- **Option C Payback Period:** 4,900 USD one-off effort / 4,500 USD net annual benefit = 1.09 years (~1.1 years / 13 months).
- **Sensitivity Analysis (Adoption reduced to 6 lecturers):**
  - Marking time saved: 6 lecturers x 1 h x 30 weeks x 10 USD = 1,800 USD.
  - Option B: Annual SaaS cost = 6 x 15 x 12 = 1,080 USD. Net annual benefit = 1,800 - 1,080 = 720 USD.
  - Option C: Annual benefits = 1,800 USD (marking) + 1,080 USD (SaaS avoided) = 2,880 USD. Net annual benefit = 2,880 - 300 = 2,580 USD. Payback period = 4,900 / 2,580 = 1.90 years (~1.9 years). Even under conservative departmental adoption, the project achieves full payback in under 2 academic years.

For raw lines and exact spreadsheet formulas, see [business-case.csv](business-case.csv).

## 4. Benefits not priced
- **Pedagogical Capstone Outcomes:** Provides four senior software engineering students with hands-on, end-to-end production experience in real-time WebSockets, microservices, containerization, and automated CI/CD.
- **Data Sovereignty and Privacy:** All student academic performance records, identifiers, and assessment results remain strictly hosted on university-controlled infrastructure, fulfilling data privacy compliance without foreign cloud transfers.
- **Unlimited Participant Concurrency:** No commercial per-seat subscription tiers or artificial participant caps restricting classroom sizes.
- **Curriculum Customization:** Direct alignment with departmental needs, allowing custom question authoring, Khmer language font rendering, and local grading exports.

## 5. Risks per option

### Option A (Do nothing)
1. **Instructional Inefficiency & Faculty Burnout:** Instructors remain overburdened with 300 hours of repetitive clerical marking each year.
2. **Student Disengagement:** Lack of interactive classroom engagement tools leads to decreased lecture attendance and delayed intervention for struggling students.

### Option B (Buy SaaS)
1. **Recurring Budgetary Inflation & Currency Risk:** Commercial SaaS vendors frequently increase educational tier pricing, exposing the department to unbudgeted annual cost hikes and foreign exchange volatility.
2. **Data Governance & Vendor Lock-in:** Student identifiers and performance metrics are hosted on third-party overseas cloud infrastructure, creating potential regulatory friction with university data protection policies.

### Option C (Build Realtime Quiz)
1. **Project Execution & Schedule Risk:** Student developers may encounter technical challenges with complex real-time WebSocket state management, risking milestone delivery deadlines.
2. **Post-Launch Maintenance Burden:** Internal IT operations must maintain the software stack, deploy patches, and manage database integrity without a dedicated vendor support contract.

## 6. Recommendation and review gate
**Recommendation:** Proceed with **Option C (Build Realtime Quiz)**. Option C provides the highest return on investment with a rapid payback period of 1.1 years (and 1.9 years under conservative 6-lecturer sensitivity), eliminates ongoing commercial subscription expenditure, keeps student data securely on-campus, and yields high educational value for the engineering department.

**Review Gate:** The project will enforce a decisive review gate at the **Week 7 MVP Demonstration**. If the student team fails to deliver all core Must features (quiz authoring, live session synchronization, real-time scoring, and leaderboard) with verified stability, the sponsor will immediately activate Option B (procuring commercial SaaS licenses) for the following semester, while scoping the internal build into a non-critical multi-semester research initiative.
