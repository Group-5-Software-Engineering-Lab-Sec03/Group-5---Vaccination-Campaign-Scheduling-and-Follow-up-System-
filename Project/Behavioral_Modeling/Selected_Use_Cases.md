# Selected Use Cases - Lab 6, Behavioral Modeling

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

## Exercise 1: Selected use cases

| Use Case ID | Use Case Name | Primary Actor | Purpose | Reason for Selection |
|---|---|---|---|---|
| UC-02 | Cancel Appointment | Patient | A patient cancels an upcoming appointment. The slot is released immediately and, if a waitlist exists, the next waitlisted patient is notified (FR-04, FR-05). | Core scheduling function that involves five classes (Cancellation, Appointment, AppointmentSlot, Waitlist, Notification) and the Patient actor. It has a natural condition (only a booked appointment can be cancelled), an optional waitlist step and a repeated step if a notification fails. |
| UC-__ | (partner 1: use case name) | (primary actor) | (purpose) | (reason for selection) |
| UC-__ | (partner 2: use case name) | (primary actor) | (purpose) | (reason for selection) |

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help format this document into proper Markdown table syntax.
