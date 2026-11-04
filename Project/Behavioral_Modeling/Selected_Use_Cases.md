# Selected Use Cases - Lab 6, Behavioral Modeling

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

## Exercise 1: Selected use cases

| Use Case ID | Use Case Name | Primary Actor | Purpose | Reason for Selection |
|---|---|---|---|---|
| UC-02 | Cancel Appointment | Patient | A patient cancels an upcoming appointment. The slot is released immediately and, if a waitlist exists, the next waitlisted patient is notified (FR-04, FR-05). | Core scheduling function that involves six classes (Patient, Appointment, Cancellation, AppointmentSlot, Waitlist, Notification). It has a natural condition (only a booked appointment can be cancelled), an optional waitlist step and a repeated step if a notification fails. It also covers the cancellation operations that were missing from the Lab 5 class diagram. |
| UC-08 | Book Appointment | Patient | A patient picks an available time slot and makes a booking. A time slot becomes unavailable, an Appointment object becomes confirmed and generated, a confirmation message is sent to the patient, and a reminder is scheduled when there are at least 3 days left before an appointment (FR-08, FR-16). | Core functionality and the first increment of the Incremental Model (Process_Model.md). Five classes are involved (Patient, AppointmentSlot, Appointment, Notification, AppointmentReminder), the guard condition is present (the slot should still be available), a retry loop is used when the slot is already booked or a notification can not be sent, and the reminder part is optional (Lab 3 relationship R-04). |
| UC-11 | Administer Vaccine Dose | Nurse | The nurse verifies eligibility, administers the dose, logs it, updates the patient's history and triggers the next-dose reminder if applicable. | Core clinical function, since it is the step where the vaccination actually happens. Three classes are involved (Appointment, Patient, Notification), the guard condition is present (the patient should be eligible), a retry loop is used when the reminder can not be delivered, and the reminder part is optional (only when a next dose is required). |
| UC-09 | Reschedule Appointment | Patient | A patient moves an existing appointment to a new time slot. The new slot is booked first, then the old slot is released, and the reminder is updated (FR-09). | It is a core patient function and it includes Book Appointment (relationship R-02). Five classes are involved (Patient, Appointment, AppointmentSlot, AppointmentReminder and the old and new slots). It has a guard (the new slot must be available), a loop over the old reminders and an optional new reminder. |

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help format this document into proper Markdown table syntax.
