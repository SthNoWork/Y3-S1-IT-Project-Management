# Lab-03: Life Cycle Selection and Tailoring Decision Record
**Course:** IT Project Management · Chapter 03  
**Standards:** PMBOK 7 · Scrum Guide 2020 · PRINCE2 7  
**Tools:** Git, Markdown editor with Mermaid preview, Spreadsheet software (Excel / Calc), draw.io (optional)  
**Estimated Time:** ~4–5 hours (5 core tasks + 1 challenge)  
**Git Branch:** `lab-03`  
**Deadline:** Nov 10, 2026, 11:59 PM

---

## 1. Overview & Context

You will characterise the **Realtime Quiz** project across five selection criteria, quantitatively compare Waterfall, Pure Scrum, and a Hybrid approach with weighted scoring, author a Tailoring Decision Record (TDR), map a 14-week hybrid life cycle in Mermaid Gantt with phase gates ($G1$–$G4$), configure Scrum mechanics for a 4-student team, and define governance (stage-gate checklists, tolerances, and closure).

### Reused Project Parameters (from Lab 01 & Lab 02)
* **Sponsor:** Head of the IT department.
* **Project Manager:** Supervising lecturer (outside the Scrum team).
* **Team:** 4 students, ~10 h/week each (560 hours total across 14 weeks).
* **Duration:** 14 weeks; Week 1 starts Tuesday, 2026-09-29.
* **Budget:** Linode VPS at gicitc.com (~$25/month), single domain, optional paid tooling.
* **Key Deadlines:** Approved plan by end of Week 3 ($G1$); 50-student pilot in Week 14 ($G4$).
* **MVP Must Features:**
  * Quiz authoring: multiple-choice questions (`FR-Q1`–`FR-Q4`)
  * Real-time participation (`FR-S1`–`FR-S7`)
  * Instant feedback & scoring (`FR-C1`–`FR-C3`)
  * Live leaderboard (`FR-S8`, `FR-C4`)
  * WebSocket broadcast updates
  * Authentication & role-based access (`FR-A1`–`FR-A3`)
  * Per-question countdown timer (`FR-Q3`, `FR-S5`)
  * Concurrent sessions (`FR-S2`)
* **Should/Could Features:** Responsive UI, analytics dashboard (`FR-R1`–`FR-R3`), CSV/PDF export (`FR-R4`), notifications (`FR-N1`, `FR-N2`), multimedia in questions/chat (`FR-N3`), guest join, question bank, admin panel.
* **Known Risks:** Campus proxy blocking WebSockets; Spring Boot 4 documentation mismatches; scope creep from Could items; race conditions during concurrent late submissions.
* **Team Experience:** First formal Scrum project; Java/Spring learned concurrently.

---

## 2. Target Deliverable Structure

Create and work inside the `lab03/` directory of your Git repository:

```text
realtime-quiz-pm/
└── lab03/
    ├── project-profile.md            # Task 1: Scored selection criteria
    ├── approach-comparison.md        # Task 2: Waterfall vs Scrum vs Hybrid
    ├── approach-scoring.csv          # Task 2: Weighted scoring sheet (+ .xlsx optional)
    ├── tailoring-decision-record.md  # Task 3: ADR-style record with phase gates
    ├── life-cycle.mmd                # Task 3: Mermaid Gantt diagram (14 weeks, G1-G4)
    ├── life-cycle.svg                # Task 3: Rendered Gantt diagram export
    ├── scrum-setup.md                # Task 4: Roles, calendar, DoR, DoD, Sprint Goal
    ├── sprint-1-backlog.csv          # Task 4: Sprint 1 backlog
    ├── governance.md                 # Task 5: Gate checklists, tolerances, closure
    ├── README.md                     # Task 5: Manifest, inputs reused, change log
    └── challenge/                    # (Optional Challenge)
        ├── sprint-1-planning.md
        ├── burndown.mmd
        ├── retrospective-template.md
        └── prince2-comparison.md
```

---

## Task 0: Setup & Branching
1. Open terminal and create the working branch:
   ```bash
   git switch -c lab-03
   mkdir -p lab03/challenge
   ```
2. Verify Mermaid rendering in VS Code or via [mermaid.live](https://mermaid.live).

---

## Task 1: Characterise the Project on Selection Criteria
**Deliverable:** `lab03/project-profile.md` (Est. 30 min)

### Steps:
1. Create `lab03/project-profile.md` titled `# Project profile · Realtime Quiz` with links to `../lab01/project-charter.md` and `../lab02/moscow-list.md`.
2. Evaluate exactly these five criteria in order:
   1. Requirements stability
   2. Technical uncertainty
   3. Team experience with agile
   4. Contract and governance constraints
   5. Need for early delivery and feedback
3. Provide one factual evidence statement per row referencing inputs.
4. Assign an **Adaptive Score** ($1$ = predictive, $5$ = adaptive) and **Weight** ($W$) per row. Ensure $\sum \text{Weights} = 100$.
5. Compute the composite Profile index: $\text{Profile} = \frac{\sum (W \times S)}{100}$.
   * **Interpretation Bands:**
     * $< 2.5$: Predictive
     * $2.5$ – $3.5$: Hybrid
     * $> 3.5$: Agile
6. Add an optional row for *Sponsor availability* (unweighted, excluded from sum).
7. Write a **3-sentence Profile Summary** below the table detailing:
   * What kind of project this is.
   * Which two criteria dominate.
   * Which approach families Task 2 must evaluate.

### Acceptance Checklist:
- [ ] 5 criteria in exact specified order with factual evidence citations.
- [ ] Weights sum to 100; scores are integers from 1 to 5.
- [ ] Profile index correctly computed and mapped to band.
- [ ] Summary identifies the 2 dominating criteria and candidate families.

---

## Task 2: Compare Three Candidate Approaches
**Deliverables:** `lab03/approach-comparison.md`, `lab03/approach-scoring.csv` (Est. 40 min)

### Steps:
1. Create `lab03/approach-comparison.md` with a comparison matrix containing:
   * Rows: **Waterfall**, **Pure Scrum**, **Hybrid**.
   * Columns: Requirements handling, Sponsor control (governance), Week sponsor plays working quiz for the first time, Two primary risks, Profile fit.
2. Create `lab03/approach-scoring.csv`:
   * Columns: `criterion,weight,waterfall,scrum,hybrid`
   * Reuse weights from Task 1.
   * Fit score scale: $1$ (poor) to $5$ (excellent).
   * Include the final row with weighted totals: `weighted score,100,<score_w>,<score_s>,<score_h>`.
3. Perform **two sensitivity analyses** (shift weight of hardest-to-judge criterion by $\pm 10$, balancing another) and state if rankings change.
4. Author the **Recommendation** section:
   * Highlight winner and runner-up with scores.
   * Specify the exact condition under which the runner-up would be selected instead.

### Acceptance Checklist:
- [ ] Comparison table includes concrete week numbers for the first playable quiz.
- [ ] `approach-scoring.csv` reuses Task 1 weights ($\sum = 100$) and formula output matches.
- [ ] 2 sensitivity tests documented with ranking implications.
- [ ] Recommendation provides explicit condition for switching to runner-up.

---

## Task 3: Tailoring Decision Record & Life Cycle Diagram
**Deliverables:** `lab03/tailoring-decision-record.md`, `lab03/life-cycle.mmd`, `lab03/life-cycle.svg` (Est. 60 min)

### Steps:
1. Create `lab03/tailoring-decision-record.md` (`# TDR-01 · Life cycle and methodology for the Realtime Quiz project`) including:
   * **Status:** proposed / accepted, date, decision makers.
   * **Context:** 4–6 sentences summarizing context from Task 1.
   * **Options considered:** Summary and score for Waterfall, Scrum, Hybrid.
   * **Decision:** Selected option and 2 core rationales.
   * **Consequences:** Minimum 3 positive and 3 negative effects (every negative must have an actionable mitigation).
   * **Tailoring Table:** Minimum 3 rows covering: *Keep from predictive*, *Keep from agile*, *Drop*, each with reasons.
   * **Phase Gates Table:** Columns for Gate ($G1$–$G4$), Week & Date, Required evidence (2–3 measurable criteria), Decision Maker, Allowed Outcomes (`continue`, `continue with changes`, `stop`, `repeat`).
2. Author `lab03/life-cycle.mmd` as a Mermaid Gantt chart:
   * Date format: `YYYY-MM-DD`, axis format: `%d %b`, tick interval: `2week`.
   * Sections: `Predictive`, `Agile delivery`, `Release`.
   * Timeline: 14 weeks (2026-09-29 to 2027-01-04).
   * Sprints: Sprints 1 to 4 must be exactly 14 consecutive days each.
   * Milestones: Insert `:milestone` for $G1$, $G2$, $G3$, and $G4$ matching gate table dates. *(Note: Do not put colons inside task descriptions).*
3. Export SVG to `lab03/life-cycle.svg`.

### Acceptance Checklist:
- [ ] All 6 ADR sections present; negative consequences have mitigations.
- [ ] Tailoring table has $\ge 3$ rows with reasons per cell.
- [ ] `life-cycle.mmd` renders cleanly, spans 14 weeks with 4 equal 14-day sprints, and displays 4 milestones.
- [ ] Dates in the Gantt milestones match the Phase Gates table exactly.
- [ ] `life-cycle.svg` committed to repo.

---

## Task 4: Scrum Setup & Sprint 1 Backlog
**Deliverables:** `lab03/scrum-setup.md`, `lab03/sprint-1-backlog.csv` (Est. 60 min)

### Steps:
1. Create `lab03/scrum-setup.md`:
   * **Roles Matrix:** Product Owner, Scrum Master, Developers (Students A–D), Project Manager (Lecturer), Sponsor (Head of IT). Specify *Accountable for* and *Not responsible for*. Include a note resolving the dual PO/Developer role conflict.
   * **Sprint Goal:** 1 stakeholder-friendly sentence for Sprint 1 (no ticket IDs).
   * **Event Calendar (Sprint 1: 2026-10-20 to 2026-11-02):** Sprint Planning, Daily Scrum (1 row for all 10 work days), Backlog Refinement, Sprint Review (sponsor invited), Sprint Retrospective. Must respect Scrum Guide 2020 scaled timeboxes.
   * **Definition of Ready (DoR):** 5 explicit conditions (FR ID, acceptance criteria, estimate, dependencies, UI sketch/wireframe).
   * **Definition of Done (DoD):** 8–10 generic, non-feature-specific criteria. Minimum 3 criteria must be automatically checkable by CI (e.g., tests, JaCoCo coverage, build status).
2. Create `lab03/sprint-1-backlog.csv`:
   * Header: `id,item,fr_ids,priority,points,owner,acceptance_criteria`
   * Select 6 to 8 Must items from `lab02/moscow-list.md`.
   * Fibonacci points: $\le 8$ per item ($1, 2, 3, 5, 8$).
   * Given/When/Then format for acceptance criteria.
   * Sum of points must equal or be within planning velocity ($\le 30$ points for 80 team hours).

### Acceptance Checklist:
- [ ] PO and SM assigned to different students; PM and Sponsor kept outside the Scrum team.
- [ ] Event calendar dates fall strictly within Sprint 1 (2026-10-20 to 2026-11-02) within timeboxes.
- [ ] DoR has 5 criteria; DoD has 8–10 generic criteria ($\ge 3$ CI-verifiable).
- [ ] Backlog CSV contains 6–8 items, max 8 points each, valid FR IDs, Given/When/Then syntax, total $\le$ velocity.

---

## Task 5: Governance & Project Documentation
**Deliverables:** `lab03/governance.md`, `lab03/README.md` (Est. 60 min)

### Steps:
1. Create `lab03/governance.md`:
   * **Stage Gates ($G1$ to $G4$):** 5 measurable checklist criteria (`- [ ]`) per gate, inputs, decision maker, allowed outcomes.
   * **Tolerances Table:** Rows for *Time, Cost (hours), Scope, Quality, Risk*; Columns for *Stage 1 (W1-3), Stage 2 (W4-7), Stage 3 (W8-11), Stage 4 (W12-14)*. All values must have explicit numbers/percentages.
   * **Escalation & Exception Path:** Rule for issuing exception reports (`Devs -> SM -> PM -> Sponsor`).
   * **Reporting:** Highlight report structure (Done, Next, Risks, Tolerance Status), review as PM checkpoint, 3-line Exception Report template.
   * **Closure Criteria:** Matrix across *Acceptance, Hand-over, Lessons learned, Administrative closure* with *Criterion, Verified by, Owner*. Hand-over must list git repo, VPS credentials, and runbook.
2. Complete `lab03/README.md`:
   * Two introductory paragraphs: (1) Approach chosen & justification, (2) Sponsor governance mechanics.
   * File index table listing all 9 files with one-line summaries.
   * Inputs reused table referencing Lab 01 and Lab 02 files.
   * Change log entry: `YYYY-MM-DD · 0.1 · Lab-03 · life cycle selection, Scrum setup and governance added`.

### Acceptance Checklist:
- [ ] 4 gate checklists with 5 measurable criteria each; dates match Gantt milestones.
- [ ] Tolerance matrix contains numbers/percentages across all cells.
- [ ] Closure table explicitly covers repo, VPS access, runbook, retrospectives, and workshop.
- [ ] `lab03/README.md` complete with file directory, inputs reused, and change log.

---

## ★ Challenge: Sprint 1 Simulation & PRINCE2 Mapping (Optional Extra Credit)
**Deliverables:** `lab03/challenge/` folder (Est. 90–120 min)

1. `sprint-1-planning.md`:
   * Record planning poker estimates for items B-01 to B-07.
   * Document convergence dialogue when high/low estimates differ by $> 1$ Fibonacci step.
   * Commit capacity checks (~80 h total, $1\text{ pt} \approx 2.5\text{ h}$).
2. `burndown.mmd`:
   * Build Mermaid `xychart-beta` containing Ideal vs Actual burndown across D0 to D10.
   * Answer: Day team was 2 days behind, velocity achieved, unfinished item returning to backlog, updated forecast for Sprints 2–4 ($120\text{ pts} - \text{velocity}$).
3. `retrospective-template.md`:
   * Complete Sprint 1 retrospective with data, positive takeaways, improvement areas, and $\ge 2$ actionable adjustments derived from burndown bottlenecks.
4. `prince2-comparison.md`:
   * Matrix mapping $\ge 10$ hybrid concepts to PRINCE2 7 equivalents.
   * Analysis paragraph on governance features PRINCE2 adds.
   * Analysis paragraph on overhead/processes PRINCE2 makes heavier.

---

## 3. Grading Rubric & Automatic Deductions

| Component | Points | Full Marks Criteria |
| :--- | :---: | :--- |
| **Task 1: Project Profile** | 10 | 5 criteria with factual evidence, weights sum to 100, correct profile score/band, summary names dominating criteria. |
| **Task 2: Comparison & Scoring** | 15 | Complete matrix with week numbers, formulas match, 2 sensitivity tests, recommendation with explicit switching rule. |
| **Task 3: Decision Record & Gantt** | 25 | All 6 ADR sections, mitigated risks, tailoring matrix with justifications; Gantt renders 4 equal sprints and matching $G1$–$G4$ milestones. |
| **Task 4: Scrum Setup** | 20 | Clean separation of roles, dated event calendar within timeboxes, generic DoD with $\ge 3$ CI items, DoR, valid backlog $\le$ velocity. |
| **Task 5: Governance & Lab Record** | 20 | Measurable stage gates, numeric tolerances across all stages, closure criteria complete, clean `README.md` with change log. |
| **Document & Diagram Quality** | 10 | Date and naming consistency across files, valid Markdown tables, committed SVG, descriptive Git commits, 0 leftover `TODO`s. |
| **★ Challenge (Extra Credit)** | +20 | Poker debates documented, burndown rendered and analyzed, retrospective complete, $\ge 10$ PRINCE2 elements mapped with 2 tailored paragraphs. |
| **Total** | **100 (+20)** | |

### Penalty Deductions:
* **-10 pts:** Decision record selects an approach contradicting the Task 2 weighted score without explicit justification.
* **-5 pts:** Each gate missing from Gantt (`:milestone`) or date mismatch between Gantt, gates table, and `governance.md`.
* **-5 pts:** Backlog item missing FR ID, item $> 8$ points, or total points exceeding velocity.
* **-5 pts:** Any DoD criterion that is feature-specific rather than generic.
* **-5 pts:** Sprints in Gantt not equal to 14 days or longer than 4 weeks.
* **-5 pts:** `lab03/README.md` missing files or change log row.
* **-3 pts:** Any tolerance listed without an explicit number or percentage.

---

## 4. Submission & Verification Checklist

Run these self-checks from the repository root before submitting:

```bash
# 1. Verify 4 milestones exist in Gantt
test $(grep -c ":milestone" lab03/life-cycle.mmd) -eq 4 && echo "Milestones OK" || echo "Fail: Must have 4 milestones"

# 2. Verify Sprint 1 Backlog item count is between 6 and 8
backlog_count=$(grep -c "^B-" lab03/sprint-1-backlog.csv)
[ "$backlog_count" -ge 6 ] && [ "$backlog_count" -le 8 ] && echo "Backlog count OK ($backlog_count)" || echo "Fail: Backlog count is $backlog_count"

# 3. Verify README references all 9 deliverables
test $(grep -c "^| lab03/" lab03/README.md) -ge 9 && echo "README files OK" || echo "Fail: Less than 9 files listed"

# 4. Check for any forgotten placeholder TODOs
grep -rl "TODO" lab03 && echo "Fail: Found lingering TODO markers" || echo "TODO check passed: None found"
```

### Git Merge Request:
* Branch: `lab-03` pushed to remote.
* Merge Request Title: `Lab-03 – <Your Full Name>`
* Merge Request Description: Include the weighted scores table and the selected life cycle approach.