# Component Descriptions - Lab 8, Exercise 3

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

The architecture has 5 components arranged in 3 layers. Layer 1: CO1 Access Management and CO4 Notification and Reminders. Layer 2: CO2 Appointment Scheduling. Layer 3: CO3 Clinical Care and CO5 Follow-up and Reporting.

| ID | Component Name | Responsibilities | Supported Functionality (Lab 3) |
|---|---|---|---|
| CO1 | Access Management | Manages the accounts of patients, nurses and clinic staff: registration, login and logout, and the patient profile. Stores roles and their permissions, lets authorized clinic staff assign or revoke roles, and limits what each user can see or do. Patient actions that book, reschedule or cancel appointments are passed on to Appointment Scheduling, and the nurse's clinical actions to Clinical Care. | FR-06 (register an account), FR-10 (view vaccination history), FR-19 and FR-20 (assign roles and role-based access), NFR-17 (role-based access) |
| CO2 | Appointment Scheduling | Manages vaccine catalog metadata (total doses, intervals, boosters), checks and updates appointment slot capacity, handles appointment booking, rescheduling, and cancellation, and manages ordered waitlists to notify the next patient when a slot opens. | FR-03 (vaccine reference data), FR-04 (cancel an appointment), FR-05 (waitlist), FR-07 (search slots), FR-08 (book), FR-09 (reschedule) |
| CO3 | Clinical Care | Checks that a patient is eligible for a dose (no active contraindication and the minimum interval since the last dose is met) before a dose can be given. Records the administered dose with batch number, injection site and time, and updates the patient's history. Records contraindications, deferrals (marking the appointment as deferred) and adverse reactions linked to the dose. | FR-02 (record a dose), FR-11 (verify eligibility), FR-12 (complete the appointment), FR-13 (contraindications), FR-14 (defer a dose), FR-15 (adverse reactions) |
| CO4 | Notification and Reminders | Sends the notifications such as the booking confirmation and the slot-available message to a waitlisted patient, and retries a delivery that fails. Schedules the appointment reminder a certain days before the visit and the overdue-dose reminder, and cancels a reminder when it is no longer needed, for example when staff override an overdue flag. | FR-05 (notify the waitlisted patient), FR-08 (booking confirmation), FR-16 (reminder 3 days before the visit), NFR-18 (reminder delivery and retry) |
| CO5 | Follow-up and Reporting | Finds patients whose next dose is overdue by using the vaccine dose intervals, and stores them as overdue flags. Lets clinic staff review a flag and override it with a recorded reason, which cancels the pending overdue reminder. Resolves flags when the missed dose is given. Produces the daily appointment dashboard and the summary report of doses, bookings and overdue patients for clinic staff. | FR-01 (review and override an overdue flag), FR-17 (summary report), FR-18 (daily dashboard) |

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help draft this document and format it into Markdown table syntax.
