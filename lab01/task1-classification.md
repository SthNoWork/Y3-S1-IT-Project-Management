# Task 1: project, operation or programme?

| # | Initiative | Temporary? | Unique? | Coordinated? | Class | Justification |
|---|------------|------------|---------|--------------|-------|---------------|
| 1 | Build the Realtime Quiz platform and pilot it with 50 students in week 14 | yes | yes | no | Project | It has a definite end date (week 14) and creates a brand-new software system that did not previously exist. |
| 2 | Run the nightly backup of the gicitc.com PostgreSQL database | no | no | no | Operation | It repeats on a recurring daily cycle with identical outputs and no planned termination date. |
| 3 | Move the department's three web servers to a new Linode region before 15 December | yes | yes | no | Project | It is bound to a hard completion deadline (15 December) and terminates once the one-off infrastructure relocation is complete. |
| 4 | Answer helpdesk tickets within the 4-hour service level | no | no | no | Operation | It is an ongoing, continuous support function operating under an indefinite service level target. |
| 5 | "Digital classroom": Realtime Quiz, LMS upgrade and lecture capture sharing one login and one grade export | yes | yes | yes | Programme | It groups multiple related projects coordinated together to achieve strategic benefits (unified authentication and grade synchronization) unattainable independently. |
| 6 | Apply the monthly security patches to the VPS | no | no | no | Operation | It is a routine, repetitive monthly maintenance cycle required to sustain baseline server security. |
| 7 | Add multi-node scaling (RabbitMQ relay, Redis registry) to Realtime Quiz next semester | yes | yes | no | Project | It is a time-boxed future initiative delivering a distinct new architectural capability to an existing platform. |
| 8 | Operate the Realtime Quiz platform after go-live: password resets, restarts, monitoring | no | no | no | Operation | It represents continuous ongoing day-to-day administration and operational upkeep with no scheduled end date. |
| 9 | Write and publish the department's annual IT report for the dean by 31 January | yes | yes | no | Project | It has a strict deadline (31 January) and yields a unique yearly publication containing fresh data and analysis. |
| 10 | Replace 40 wireless access points in two buildings during the summer break | yes | yes | no | Project | It is confined to the summer break window and concludes when the defined set of 40 physical access points is installed. |

## Grey zones
- **#7 (Add multi-node scaling):** This initiative could be classified as an operational software maintenance enhancement or as a standalone project. The deciding information that would settle it is whether the sponsor formally funds and charters it with a separate dedicated budget, team, and discrete start/finish dates, rather than absorbing the feature backlog into routine operational software upkeep.
- **#9 (Annual IT report):** This initiative repeats every year as a cyclical obligation, yet each annual edition is unique and governed by a hard deadline (31 January). The deciding information that would settle it is whether departmental leadership treats it as a designated small annual project with a dedicated coordinator and temporary effort allocation, or as an unbudgeted routine duty performed within someone's standing job description.

## What our project hands over
Upon go-live in week 14, the Realtime Quiz project hands over ongoing platform operations to the IT department's central operations team (specifically the VPS administrator for gicitc.com). The operations team assumes responsibility for routine server restarts, daily PostgreSQL backups, application uptime monitoring, and tier-2 student/instructor account support. To run the platform reliably, operations requires an operational runbook, the production `docker-compose.prod.yml` configuration with environment variable guidelines, and a tested database backup and restore procedure.