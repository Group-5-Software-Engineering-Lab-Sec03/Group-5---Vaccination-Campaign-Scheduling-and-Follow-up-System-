# Work Breakdown Structure (WBS)

| **ID** | **Task Name** | **Description** | **Predecessor(s)** | **Duration (Days)** |
| --- | --- | --- | --- | --- |
| T1 | Requirements and Model Review | Review the 20 FRs, 20 NFRs, 20 use cases and 5 scenarios against the project scope, and check that each use case is traceable to at least one FR. Resolve the known inconsistencies such as replacing UC-04 with "Review Flagged Patient" so relationship R-01 refers to an existing use case, merge the leave waitlist function into UC-03 (Manage Appointment Waitlist), and decide whether role management belongs to a System Admin or to Clinic Staff, since FR-19, FR-20 and UC-18 disagree with the Use Case Diagram. Update the requirements documents in the GitHub repository so later design work uses one agreed version. | None | 3 |
| T2 | Development Environment and Database Setup | Finalize the Context Diagram using the external entities confirmed in T1, which come from the final use case actors, and define their incoming and outgoing data flows. Finalize the Level-0 DFD with processes P1 to P6 and data stores D1 to D4, and complete the Core Processes Matrix with the inputs, outputs and rules for each process. Check that the Context Diagram and Level-0 DFD are balanced and that every flow name matches across the diagrams and the matrix, so the process and data store boundaries are fixed before database and module design start. | T1 | 2 |
| T3 | Database schema design | Design the tables, keys and relationships for D1 Users and Roles, D2 Appointments and Waitlist, D3 Vaccination Records and D4 Vaccine Schedule Reference. | T2 | 3 |
| T4 | Vaccine Reference Data Setup | Load each vaccine type with its required doses, recommended interval and booster flag (FR-03) in D4, so the flagging and eligibility logic can use the correct schedule per vaccine. | T3 | 2 |
| T5 | Patient Interface Design | Design structural blueprint for registration, login, slot search, booking, rescheduling, cancellation, waitlist and vaccination history. | T1 | 3 |
| T6 | Nurse and Staff Interface Design | Design interaction specifications for the nurse dose workflow (eligibility check, administration, deferral, adverse reaction), the staff dashboard, overdue list and reports. | T1 | 3 |
| T7 | Authentication and Role Management | Implement registration, login and access based on roles for Patient, Nurse and Clinic Staff. | T3 | 5 |
| T8 | Appointment and Waitlist Module | Implement slot search, booking, rescheduling, cancellation, no-show marking and waitlist handling. | T4, T5, T7 | 8 |
| T9 | Eligibility and Dose Administration Module | Implement eligibility checks, dose logging, contraindications, deferrals and adverse reactions. | T4, T6, T7 | 7 |
| T10 | Overdue Flagging Orchestration | Implement vaccine overdue detection and the staff override with a recorded reason. | T4, T9 | 6 |
| T11 | Reminders and Notifications | Implement appointment reminders 3 days ahead, overdue reminders and waitlist slot notifications. | T8, T10 | 5 |
| T12 | Dashboard, History and Reports | Implement the staff dashboard, patient vaccination history and clinic summary reports. | T8, T9 | 6 |
| T13 | System Integration | Connect all modules to the database and to each other, and fix interface problems. | T10, T11, T12 | 4 |
| T14 | Testing | Run test cases against the FRs and NFRs, and fix defects. | T13 | 6 |
| T15 | Deployment Preparation and User Guide | Prepare the deployment and write the user guide and final documentation. | T14 | 3 |

**Note on AI tool use (Claude):** This risk register template was drafted with the assistance of an AI tool (Claude) to help with the structure and format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.