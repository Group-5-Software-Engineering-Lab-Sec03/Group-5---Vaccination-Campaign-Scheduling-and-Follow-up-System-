| Scenario ID | Scenario Title | Actor/Stakeholder | Scenario Description |
|---|---|---|---|
| S-01 | Incorrect Overdue (False Positive) Flag on Second Dose | Clinic Staff | A patient received their second dose at a different clinic branch, but the record was entered into the system two days late. Before the entry was made, the system automatically flagged the patient as "overdue" and generated a reminder notification. A staff member reviewing the flagged list notices the flag, checks the patient's medical record, finds the dose was already administered, and manually corrects the record by clearing the false positive flag and cancelling the pending reminder. |

**Note on AI tool use (Claude):** This scenario was drafted with the assistance of an AI tool (Claude) to help with the structure and format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.


## Sara Alhammadi (g00101461) Contributions

| Scenario ID | Scenario Title | Actor/Stakeholder | Scenario Description |
|---|---|---|---|
| S-03 | Nurse Administers Dose During Clinic Visit | Nurse | 1. A nurse pulls up a patient's profile during a scheduled visit.<br>2. The nurse checks that the patient is eligible for the next dose (no flagged contraindications, correct interval since last dose).<br>3. The nurse administers the vaccine.<br>4. The nurse logs the batch/lot number and administration site.<br>5. The system updates the patient's vaccination history and automatically schedules the reminder for the next dose if one is required. |

## Maaziya Contributions

| Scenario ID | Scenario Title | Actor/Stakeholder | Scenario Description |
|---|---|---|---|
| S-02 | Patient Books and Manages Vaccine Appointment | Patients | 1. A patient registers an account.<br>2. The patient searches for available appointment slots for a specific vaccine.<br>3. The patient books a slot, and the system confirms the booking and updates availability.<br>4. The patient later needs to reschedule the appointment due to a personal conflict.<br>5. The system processes the reschedule and reflects the change in the patient's appointment history. |

## Ahmed Contributions

| Scenario ID | Scenario Title | Actor/Stakeholder | Scenario Description |
|---|---|---|---|
| S-04 | Patient Receives Appointment and Overdue Reminders | Patients | 1. Patient has an upcoming second-dose appointment.<br>2. He receives an automated reminder 3 days in advance.<br>3. Another patient missed their window for a dose and was flagged overdue.<br>4. They receive a reminder to book a follow-up appointment.<br>5. The system logs these reminder events against both patients' records. |