| UC ID | Use Case Name | Primary Actor | Short Description | Contributor |
|---|---|---|---|---|
| UC-01 | Correct Missed Dose Flag | Clinic Staff | Staff reviews a patient flagged as overdue and verifies the actual dose record. If the flag is a false positive, Clinic Staff overrides it and cancels the associated reminder, else if the flag is a true positive, no action is taken and the reminder proceeds. | [Saif Almas] |

**Note on AI tool use (Claude):** This use case was drafted with the assistance of an AI tool (Claude) to help with the structure and format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.


## Sara Alhammadi (g00101461) Contributions

| UC ID | Use Case Name | Primary Actor | Short Description | Contributor |
|---|---|---|---|---|
| UC-11 | Administer Vaccine Dose | Nurse | A nurse verifies patient eligibility, administers the dose, and logs administration details, updating the patient's history and triggering the next-dose reminder if applicable. | Sara |
| UC-12 | Verify Patient Eligibility for Dose | Nurse | A nurse checks a patient's vaccination history and dosing schedule to confirm they are due and eligible, flagging any conflict for review before proceeding. | Sara |
| UC-13 | Record Patient Contraindication | Nurse | A nurse adds a contraindication (e.g. allergy or pregnancy) to a patient's profile, specifying the affected vaccine(s). The system stores it and uses it to warn during future eligibility checks. | Sara |
| UC-14 | Defer Vaccine Dose | Nurse | When a patient is found ineligible or declines the dose, the nurse selects a deferral reason. The system marks the appointment as "Deferred" and keeps it in the patient's history. | Sara |
| UC-15 | Record Adverse Reaction | Nurse | After a dose, the nurse records any reaction observed (symptoms, severity, onset time, action taken). The system links it to that dose in the patient's history. | Sara |

### Use Case Relationships (involving Sara's Use Cases)

| Relationship ID | Base Use Case | Related Use Case | Type | Justification |
|---|---|---|---|---|
| R-03 | Administer Vaccine Dose | Verify Patient Eligibility for Dose | `<<include>>` | Administering a dose always requires first verifying eligibility. It is not optional, so it is an include, not an extend. |
| R-06 | Verify Patient Eligibility for Dose | Defer Vaccine Dose | `<<extend>>` | Deferral only happens when the eligibility check fails or the patient declines. It is conditional, and a successful check never triggers it. |
| R-07 | Administer Vaccine Dose | Record Adverse Reaction | `<<extend>>` | Most administrations have no reaction, so recording one is optional behavior that occurs only when a reaction is observed. |
