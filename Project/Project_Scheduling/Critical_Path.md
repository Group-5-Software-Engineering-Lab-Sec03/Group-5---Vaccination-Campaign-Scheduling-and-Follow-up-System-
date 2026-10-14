# Critical Path – Vaccination Scheduling System

**Critical Path:** T1 → T2 → T3 → T7 → T9 → T10 → T11 → T13 → T14 → T15

**Expected Project Duration:** 44 days

| Task | D | ES | EF | LS | LF | Slack |
|---|---|---|---|---|---|---|
| T1 | 3 | 0 | 3 | 0 | 3 | 0 |
| T2 | 2 | 3 | 5 | 3 | 5 | 0 |
| T3 | 3 | 5 | 8 | 5 | 8 | 0 |
| T4 | 2 | 8 | 10 | 11 | 13 | 3 |
| T5 | 3 | 3 | 6 | 14 | 17 | 11 |
| T6 | 3 | 3 | 6 | 10 | 13 | 7 |
| T7 | 5 | 8 | 13 | 8 | 13 | 0 |
| T8 | 8 | 13 | 21 | 17 | 25 | 4 |
| T9 | 7 | 13 | 20 | 13 | 20 | 0 |
| T10 | 6 | 20 | 26 | 20 | 26 | 0 |
| T11 | 5 | 26 | 31 | 26 | 31 | 0 |
| T12 | 6 | 21 | 27 | 25 | 31 | 4 |
| T13 | 4 | 31 | 35 | 31 | 35 | 0 |
| T14 | 6 | 35 | 41 | 35 | 41 | 0 |
| T15 | 3 | 41 | 44 | 41 | 44 | 0 |

## Explanation
The Critical Path is the longest chain of dependent tasks. Every task on it has
Slack = LS − ES = 0, so a delay in any of them delays the whole project.
T7, T9, T10 and T11 are critical because each sets the start of its successor
(T9 starts at max(10, 6, 13) = 13; T10 at max(10, 20) = 20; T11 at max(21, 26) = 26;
T13 at max(26, 31, 27) = 31).

## Verification
Verified using Microsoft Excel
Both gave the same critical path and a 44-day duration, matching the manual
calculation. See `Lab_4_Ex_7_Verified.xlsx` and the screenshots in this folder.

