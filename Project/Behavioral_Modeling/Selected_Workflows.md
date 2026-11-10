# Selected Workflows - Lab 7, Activity Diagram Modeling

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

## Exercise 1: Selected workflows

| Use Case ID | Use Case Name | Primary Actor | Workflow Modeled | Control-Flow Elements Used | Swimlanes |
|---|---|---|---|---|---|
| UC-02 | Cancel Appointment | Patient | The patient requests a cancellation and the appointment status is checked. If the appointment is booked, a cancellation record is created and the slot is released. The waitlist is then checked and, if it is not empty, the next waitlisted patient gets a slot-available notification, which is repeated until it is delivered. The patient finally receives the cancellation confirmation (FR-04, FR-05). | Initial node, 3 decision nodes (booked / not booked, waitlist empty / waitlist not empty, delivered / delivery failed), 1 merge node, 2 final nodes. No fork or join, because every step depends on the one before it. | Patient, Appointment, Cancellation, AppointmentSlot, Waitlist, Notification |
| UC-11 | Administer Vaccine Dose | Nurse | The nurse requests to administer a dose and the patient's eligibility is checked (contraindications and minimum interval). If the patient is not eligible, the nurse sees a not-eligible message and the dose is not given. If the patient is eligible, the nurse administers the dose, the dose is recorded with its batch number and injection site in the patient's vaccination history, and the appointment is marked completed. If a next dose is required, a next-dose reminder is scheduled and sent, and the sending is repeated until it is delivered. The nurse finally receives the dose-recorded confirmation (FR-03, FR-11, FR-16). | Initial node, 3 decision nodes (eligible / not eligible, next dose required / not required, delivered / delivery failed), 1 merge node, 2 final nodes. No fork or join, because every step depends on the one before it. | Nurse, EligibilityChecker, VaccinationDose, Appointment, AppointmentReminder. |

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help format this document into proper Markdown table syntax.
