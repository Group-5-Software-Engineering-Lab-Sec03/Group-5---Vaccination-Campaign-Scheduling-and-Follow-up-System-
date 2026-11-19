# Architectural Design Goals - Lab 8, Exercise 1

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

| Goal ID | Design Goal | Description | Related Requirement | Priority | Justification |
|---|---|---|---|---|---|
| G1 | Reliability | The automatic overdue flagging and the waitlist notifications must give correct results. Few false flags and no flag when the dosing data is missing, and notifications sent in the right queue order. | NFR-01, NFR-05 | High | A wrong flag sends reminders to patients who are already vaccinated, and an out-of-order waitlist notification gives a freed slot to the wrong patient, so clinic staff would stop trusting the system. |
| G2 | Performance | Searching and booking appointment slots must finish quickly. | NFR-07 | Medium | Patients and staff wait on the screen while slots load, so slow searches waste time. |
| G3 | Security | All requests are checked against role-based access control, and thus only the patient can view their record, while employees will only view the records that they are permitted to view. Permissions for role-based access control may be modified by authorized clinic staff without requiring a shutdown or code deployment. | NFR-17, NFR-08, NFR-20, FR-19, FR-20 | High | The database holds information on each individual’s health (history of vaccinations, contraindications, adverse reactions). The leak of this data is the most serious threat (R2 on the Risk Register), so the verification process has to be implemented in one and only module. |
| G4 | Scalability | The booking part of the system keeps working when many patients use it at the same time. | NFR-10 | Low | A vaccination campaign can bring many bookings on one day, but the project is limited to one clinic. |
| G5 | Availability | The nurse can still record a dose during a visit if the network connection drops, the entry is kept locally and sent again when the connection returns, so no administered dose is lost. | NFR-12, FR-12 | High | A dose is given once and cannot be repeated, so if the record is lost the patient's history becomes wrong and the next-dose reminder may never be scheduled. Clinic networks can drop during a visit. |
| G6 | Usability | The nurse must be able to finish the dose workflow in few screens, so the clinical component should offer a few complete operations (check eligibility, record the dose) and not many small steps | NFR-11, FR-11, FR-12 | Medium | A nurse sees one patient at a time during a clinic visit. Many small steps would slow the visit and affect the performance, so the interfaces of the clinical component should be straightforward. |

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help draft this document and format it into Markdown table syntax. 