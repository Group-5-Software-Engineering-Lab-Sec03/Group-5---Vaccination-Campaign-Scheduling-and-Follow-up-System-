# Consolidated Class Inventory 

21 classes. Contributors come from the individual diagrams in the shared Word document. UC and FR numbers are taken from the team's Use_Cases.md and Functional_Requirements.md.

| # | Class | Package | Contributors | Use cases | Key responsibility |
|---|---|---|---|---|---|
| 1 | User (abstract) | Accounts | Maaziya, Sara, Ahmed | UC-06 | Common identity and login for all roles |
| 2 | Role | Accounts | Ahmed | UC-18 | Named set of permissions, assignable to users |
| 3 | Patient | Accounts | All | UC-02, UC-03, UC-06 to UC-10 | Patient account and booking actions |
| 4 | Nurse | Accounts | Sara | UC-11 to UC-15 | Administers doses and records eligibility, contraindications, deferrals and reactions |
| 5 | ClinicStaff | Accounts | Saif, Ahmed | UC-01, UC-05, UC-17, UC-18, UC-20 | Staff actions such as override flags, dashboard, reports, roles |
| 6 | Appointment | Scheduling | All | UC-02, UC-05, UC-08, UC-09, UC-11, UC-14 | A booked visit for one dose |
| 7 | AppointmentSlot | Scheduling | Maaziya, Saif | UC-02, UC-07, UC-08, UC-09 | A bookable time with capacity |
| 8 | Waitlist | Scheduling | Saif | UC-03 | Ordered queue for a full slot (join and leave) |
| 9 | Cancellation | Scheduling | Saif | UC-02, UC-05 | Record of a cancelled or missed appointment, releases the slot |
| 10 | Vaccine | Clinical | Maaziya, Sara | UC-07, UC-12 | Vaccine type, doses and intervals (D4) |
| 11 | VaccinationDose | Clinical | Sara | UC-10, UC-11 | One administered dose (D3) |
| 12 | EligibilityChecker | Clinical | Sara | UC-12 | Applies contraindication and interval rules |
| 13 | Contraindication | Clinical | Sara | UC-13 | Medical reason blocking a vaccine |
| 14 | Deferral | Clinical | Sara | UC-14 | Postponement or refusal on the day |
| 15 | AdverseReaction | Clinical | Sara | UC-15 | Reaction after a dose |
| 16 | OverdueFlag | Follow-up | Saif, Ahmed | UC-01, UC-19 | Flags a missed dose, supports staff override |
| 17 | Notification | Follow-up | Saif, Ahmed | UC-03, UC-16, UC-19 | Message delivery with status |
| 18 | AppointmentReminder | Follow-up | Ahmed | UC-16 | Scheduled reminder, subclass of Notification |
| 19 | OverdueReminder | Follow-up | Ahmed | UC-19, UC-01 | Reminder tied to a flag, cancelled on override |
| 20 | Dashboard | Follow-up | Ahmed | UC-17 | Filtered view of the day's appointments |
| 21 | Report | Follow-up | Ahmed | UC-20 | Summary of doses, bookings and overdue patients |

**Note on AI tool use (Claude):** This document was drafted with the assistance of an AI tool (Claude) to help with the structure and to format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.