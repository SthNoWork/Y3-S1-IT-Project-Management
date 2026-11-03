# Negotiation · Sponsor asks for all Should features by week 10

## Data sheet (week 4)

| Measure | Value |
| --------------------------------------- | ------------------- |
| Capacity W5–W10 (6 weeks x 40 h) | 240 h |
| Must remaining (300 h planned - 148 h done) | 152 h |
| Should total (Task 2 rating: F09..F13) | 110 h |
| Needed by W10 = Must remaining + Should | 152 h + 110 h = 262 h |
| Shortfall by W10 (without contingency) | 22 h (0.55 weeks) |
| Shortfall by W10 (with 56 h contingency) | 78 h (1.95 weeks) |
| Velocity, sprints 1–2 (story points) | 18, 21 -> 19.5 avg |

---

## Script

**Turn 1 · Sponsor:** I need every Should feature demonstrable at the faculty open day in week 10. It is mostly small stuff, so we should easily have the whole platform running by then.

**Turn 2 · PM:** We want the department to shine at the open day. Looking at our baseline data, our remaining Must work is 152 hours across weeks 5 to 10, while our total team capacity is exactly 240 hours. Adding all 110 hours of Should scope pushes our total demand to 262 hours, which creates an immediate 22-hour deficit before touching our 56-hour contingency buffer.

**Turn 3 · Sponsor:** It is only a 22-hour difference. Your students can just work a bit harder and put in 12 hours a week instead of 10 for a couple of sprints to close the gap.

**Turn 4 · PM:** University capstone guidelines strictly limit students to 10 hours per week per student, or 40 hours total. If we increase to 12 hours, that is 48 hours over two sprints; however, historical data shows our velocity held at 19.5 points across sprints 1 and 2, and student overtime in academic settings increases defect density by over 30 %, which would threaten our zero-blocking-defect target.

**Turn 5 · Sponsor:** Other capstone teams in the department manage to deliver comprehensive feature sets early for marketing demonstrations. We cannot present an incomplete system to prospective students.

**Turn 6 · PM:** Other teams often carry larger groups or commercial templates, whereas our system is built in-house for institutional data sovereignty. If we commit 262 hours into a 240-hour envelope, we enter week 10 with negative 22 hours of buffer and zero contingency, meaning any single network bug or WebSocket disconnect would crash the live presentation in front of the prospective students.

**Turn 7 · Sponsor:** Can we just decide later around week 8 once we see how fast the team completes Sprint 3 and 4?

**Turn 8 · PM:** If we defer the decision to week 8, the team will split effort across all 5 Should features simultaneously. At that point, 80 hours will be half-finished, leaving zero features deployable if time runs short. Choosing our focus now guarantees polished, stable features.

**Turn 9 · PM:** Here are two data-backed ways to give you an impressive, rock-solid open day:
- **Counter-proposal 1:** Deliver all remaining Must features (152 h) plus Responsive Design F09 (20 h) and Analytics F10 (30 h) by week 10. That requires 202 hours out of our 240-hour capacity, leaving a healthy 38-hour safety buffer. Results Export (F11, 24 h), Notifications (F12, 12 h), and Media (F13, 24 h) remain scheduled for the week-14 pilot.
- **Counter-proposal 2:** Build a lightweight demonstration mode with pre-seeded, mocked analytics data for the open day requiring only 8 hours of work. All Should features remain on their original week-14 schedule.

**Turn 10 · Sponsor:** How good will the presentation look under Counter-proposal 1?

**Turn 11 · PM:** Counter-proposal 1 guarantees that prospective students can take live quizzes on their personal smartphones due to responsive design (F09), while you project real-time leaderboards and aggregated classroom analytics (F10) on the auditorium projector with zero lag.

**Turn 12 · Sponsor:** That gives us exactly the visual impact we need for the audience without risking a live crash. Let us proceed with Counter-proposal 1.

**Turn 13 · PM:** I will record this formally as DR-01 today and update our schedule baseline before Sprint 3 begins on Monday.
