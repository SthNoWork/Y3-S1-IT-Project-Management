# Trade-off memo · CR-03 · Pilot moves to week 12

To: Head of IT (sponsor) · From: PM (lecturer) · Date: 2026-10-13 · Decision by: W4 (2026-10-24)

## Fixed facts

- C-01: Pilot with 50 students is moved to week 12 (dean's directive of 2026-10-10).
- C-02: Team capacity is 4 students x 10 h/week = 40 h/week, providing 480 person-hours over 12 weeks.
- C-03: Cash budget is fixed at 200 USD with zero additional capital available.

## Request

The dean shortened the semester by 2 weeks. Total project capacity fell by 80 h (from 560 h to 480 h). Baseline planned work is 504 h, which exceeds 12-week capacity by 24 h before factoring in any risk. Contingency shrinks from 56 h to 48 h (10 % of 480 h). A minimum of 24 h must leave the scope immediately.

## Options

| Option | Time | Cost | Quality at week-12 pilot |
| ------ | ---- | ---- | ------------------------ |
| A Drop Could scope (94 h) | 0 weeks | 0 USD | All 8 Must and 5 Should features deliver; chat, question bank, and guest accounts deferred |
| B Pay teaching assistant for 104 h | 0 weeks | 1,248 USD | Full 17 features delivered; violates C-03 cash ceiling by 624 % |
| C Keep original week-14 pilot | +2 weeks | 0 USD | Full 17 features delivered; violates C-01 and misses semester grading deadline |

## Recommendation

Select **Option A**. Option A delivers 100 % of core Must and Should features within week 12, expends 0 USD, and creates a 70 h buffer ($480\text{ h} - 410\text{ h}$) that fully protects against development delays. Option B is rejected because spending 1,248 USD exceeds the 200 USD cash limit by 1,048 USD with no budget source. Option C is rejected because breaching the dean's week-12 deadline invalidates student capstone grades.

## If no decision by W4 (2026-10-24)

If no written decision is received by 2026-10-24, the team will execute Option A by default: all 94 h of Could scope will be removed from the baseline to protect the 8 Must features for the week-12 delivery.

Details: [change-requests.md](change-requests.md)
