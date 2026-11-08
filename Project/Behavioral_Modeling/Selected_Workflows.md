# Selected Workflows - Lab 7, Activity Diagram Modeling

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

## Exercise 1: Selected workflows

| Use Case ID | Use Case Name | Primary Actor | Workflow Modeled | Control-Flow Elements Used | Swimlanes |
|---|---|---|---|---|---|
| UC-02 | Cancel Appointment | Patient | The patient requests a cancellation and the appointment status is checked. If the appointment is booked, a cancellation record is created and the slot is released. The waitlist is then checked and, if it is not empty, the next waitlisted patient gets a slot-available notification, which is repeated until it is delivered. The patient finally receives the cancellation confirmation (FR-04, FR-05). | Initial node, 3 decision nodes (booked / not booked, waitlist empty / waitlist not empty, delivered / delivery failed), 1 merge node, 2 final nodes. No fork or join, because every step depends on the one before it. | Patient, Appointment, Cancellation, AppointmentSlot, Waitlist, Notification |

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help format this document into proper Markdown table syntax.