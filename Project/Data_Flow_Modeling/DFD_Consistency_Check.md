 DFD Consistency and Balancing Check

 1. Context Diagram ↔ Level-0 Balancing

Every external flow in the Context Diagram must appear in the Level-0 DFD, entering or leaving through an appropriate process.

| External Entity | Direction | Context Diagram Flow | Level-0 Process | Balanced |

| Patient | In | Registration / Login | 1.0 Manage Accounts & Access 
| Patient | In | Search Slots; Book / Reschedule / Cancel; Join / Leave Waitlist | 2.0 Manage Appointments & Waitlist
| Patient | In | View Vaccination History | 6.0 Provide Dashboard, History & Reports
| Patient | Out | Account Confirmation | 1.0 
| Patient | Out | Available Slots; Appointment / Waitlist Status | 2.0 | 
| Patient | Out | Vaccination History | 6.0 | 
| Patient | Out | Reminders / Notifications | 5.0 Send Reminders & Notifications 
| Nurse | In | Login | 1.0 | 
| Nurse | In | Dose Details; Eligibility / Contraindication; Deferral; Adverse Reaction Details | 3.0 Verify Eligibility & Administer Dose | 
| Nurse | Out | Eligibility Result / Warnings; Appointment / Patient Info; Dose Recording Confirmation | 3.0 | 
| Clinic Staff | In | Login / Role Management | 1.0 |
| Clinic Staff | In | Flag Review / Override | 4.0 Track Follow-up & Flag Overdue Doses 
| Clinic Staff | In | Dashboard / Report Requests | 6.0 |
| Clinic Staff | Out | Role Update Confirmation | 1.0 | 
| Clinic Staff | Out | Overdue Patient List | 4.0 | 
| Clinic Staff | Out | Dashboard; Clinic Reports | 6.0 |

No flows appear in Level-0 that leave the system without a matching Context Diagram output, and the Context Diagram has no input that is missing from Level-0.

2. Entity Consistency
Context Diagram, Level-0 DFD and the Lab 3 Use Case Diagram all use the same three actors: Patient, Nurse, Clinic Staff.
Clinic Staff also covers the administrator role (UC-18 Manage User Access Roles).

3. Structural Checks
Level-0 has 6 meaningful processes (minimum 5) and 4 data stores, D1–D4 (minimum 2).
Every process has at least one input and one output.
No data store connects directly to an external entity.
Every data flow is one-directional.
The Core Processes Matrix lists the same 6 processes (P1–P6 = 1.0–6.0).

4. Process ↔ FR / Use Case Traceability
| Process | Functional Requirements | Use Cases |

| 1.0 Manage Accounts & Access | FR-06, FR-19, FR-20 | UC-06, UC-18 |
| 2.0 Manage Appointments & Waitlist | FR-04, FR-05, FR-07, FR-08, FR-09 | UC-02, UC-03, UC-04, UC-05, UC-07, UC-08, UC-09 |
| 3.0 Verify Eligibility & Administer Dose | FR-02, FR-11, FR-12, FR-13, FR-14, FR-15 | UC-11, UC-12, UC-13, UC-14, UC-15 |
| 4.0 Track Follow-up & Flag Overdue Doses | FR-01, FR-03 | UC-01 |
| 5.0 Send Reminders & Notifications | FR-05, FR-16 | UC-16, UC-19 |
| 6.0 Provide Dashboard, History & Reports | FR-10, FR-17, FR-18 | UC-10, UC-17, UC-20 |


The Context Diagram and Level-0 DFD are balanced, use the same actors as Lab 3, and trace to the FRs and Use Cases.
