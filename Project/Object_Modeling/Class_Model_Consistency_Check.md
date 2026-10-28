# Class Model Consistency and Traceability Check

## 1. Actor consistency

| Lab 3 actor (Use Case Diagram) | Lab 4 external entity | Class model | Result |
|---|---|---|---|
| Patient | Patient | `Patient` (subclass of User) | OK |
| Nurse | Nurse | `Nurse` (subclass of User) | OK |
| Clinic Staff | Clinic Staff | `ClinicStaff` (subclass of User) | OK |

No class represents a "System Admin". FR-19, FR-20 and the Lab 4 Core Processes Matrix disagree on who manages roles. The model follows the matrix (Clinic Staff), see issue 5.

## 2. Functional requirements to classes

| FR | Requirement (short) | Classes and operations | Result |
|---|---|---|---|
| FR-01 | Review and override a dose flag, with a recorded reason | `OverdueFlag.override()`, `overrideReason`, `cancelPendingReminder()`; `ClinicStaff` "overrides" `OverdueFlag` | Gap (issue 1) |
| FR-02 | Record an administered dose (type, dose no., batch, date) | `VaccinationDose.record()`, `Nurse.administerDose()` | Gap (issue 4) |
| FR-03 | Vaccine reference data (doses, interval, booster) | `Vaccine.totalDoses`, `doseIntervalDays`, `boosterRequired` | OK |
| FR-04 | Cancel an appointment and release the slot | `Cancellation.releaseSlot()`, `AppointmentSlot.release()` | Gap (issue 2) |
| FR-05 | Notify the next waitlisted patient | `Waitlist.getNext()`, `notifyWaitlist()`, `Notification.send()` | OK |
| FR-06 | Patient registers an account | `Patient.registerAccount()`, `User` | OK |
| FR-07 | Search slots by vaccine and date | `Patient.searchSlots()`, `AppointmentSlot.isAvailable()` | OK |
| FR-08 | Book an appointment and get confirmation | `Patient.bookAppointment()`, `Appointment.confirm()`, `AppointmentSlot.book()` | OK |
| FR-09 | Reschedule an appointment | `Patient.reschedule()`, `Appointment.reschedule()` | OK |
| FR-10 | View vaccination history | `Patient.viewHistory()`, `VaccinationDose`, `Appointment` | OK |
| FR-11 | Verify identity and eligibility before a dose | `Nurse.verifyEligibility()`, `EligibilityChecker.checkEligibility()` | OK |
| FR-12 | Mark appointment completed; record nurse, site, time; schedule the next reminder | `Appointment.markCompleted()`, `VaccinationDose` (`injectionSite`, `administeredAt`), association Nurse "administers" dose, `AppointmentReminder.schedule()` | OK |
| FR-13 | Record a contraindication | `Contraindication`, `Nurse.recordContraindication()` | OK |
| FR-14 | Defer a dose with a reason | `Deferral`, `Appointment.markDeferred()`, `Nurse.deferDose()` | OK |
| FR-15 | Record an adverse reaction linked to the dose | `AdverseReaction`, `Nurse.reportReaction()`, association "has recorded reaction" | OK |
| FR-16 | Reminder at least 3 days before an appointment | `AppointmentReminder.daysBefore` | OK |
| FR-17 | Clinic summary report for a date range | `Report.generate()`, `getSummary()`, `getOverduePatients()` | OK |
| FR-18 | Daily dashboard filtered by time and vaccine type | `Dashboard.filterByTime()`, `filterByVaccine()` | OK |
| FR-19 | Assign roles and permissions | `Role`, `ClinicStaff.assignRole()` | Gap (issue 5) |
| FR-20 | Assign, change and delete role-based access | `Role.addPermission()`, `removePermission()`, `ClinicStaff.revokeRole()` | Gap (issue 5) |

## 3. Use cases to classes

| UC | Use case | Classes and operations | Result |
|---|---|---|---|
| UC-01 | Correct Missed Dose Flag | `OverdueFlag`, `OverdueReminder.cancel()`, `ClinicStaff` | Gap (issue 1) |
| UC-02 | Cancel Appointment | `Cancellation`, `Appointment`, `AppointmentSlot`, `Waitlist` | Gap (issue 2) |
| UC-03 | Manage Appointment Waitlist (join and leave; UC-04 merged) | `Waitlist.join()`, `leave()`, `Notification` | OK |
| UC-05 | Missed Appointment | `Cancellation`, `Appointment`, `ClinicStaff` | Gap (issues 1, 3) |
| UC-06 | Register Patient Account | `Patient.registerAccount()`, `User` | OK |
| UC-07 | Search Available Slots | `Patient.searchSlots()`, `AppointmentSlot`, `Vaccine` | OK |
| UC-08 | Book Appointment | `Patient.bookAppointment()`, `Appointment`, `AppointmentSlot` | OK |
| UC-09 | Reschedule Appointment | `Appointment.reschedule()`, `AppointmentSlot` | OK |
| UC-10 | View Vaccination History | `Patient.viewHistory()`, `VaccinationDose` | OK |
| UC-11 | Administer Vaccine Dose | `Nurse.administerDose()`, `VaccinationDose`, `Appointment.markCompleted()` | OK |
| UC-12 | Verify Patient Eligibility | `EligibilityChecker`, `Nurse.verifyEligibility()`, `Contraindication`, `Vaccine` | OK |
| UC-13 | Record Patient Contraindication | `Contraindication`, `Nurse.recordContraindication()` | OK |
| UC-14 | Defer Vaccine Dose | `Deferral`, `Appointment.markDeferred()` | OK |
| UC-15 | Record Adverse Reaction | `AdverseReaction`, `Nurse.reportReaction()` | OK |
| UC-16 | Send Appointment Reminder | `AppointmentReminder`, `Notification` | OK |
| UC-17 | View Staff Dashboard | `Dashboard`, `ClinicStaff.viewDashboard()` | OK |
| UC-18 | Manage User Access Roles | `Role`, `ClinicStaff.assignRole()` | Gap (issue 5) |
| UC-19 | Send Overdue Reminder | `OverdueReminder`, `OverdueFlag` | OK |
| UC-20 | Generate Clinic Report | `Report`, `ClinicStaff.generateReport()` | OK |

**Use case relationships (these ones are from lab 3):**

| Relationship | Reflected in the class model by | Result |
|---|---|---|
| Reschedule `<<include>>` Book | `Appointment.reschedule()` books the new slot through `AppointmentSlot.book()` before releasing the old one | OK |
| Administer Dose `<<include>>` Verify Eligibility | `Nurse.administerDose()` relies on `EligibilityChecker` | OK |
| Administer Dose `<<extend>>` Record Adverse Reaction | `AdverseReaction` is optional (0..*) per `VaccinationDose` | OK |
| Verify Eligibility `<<extend>>` Defer Dose | `Deferral` is optional (0..*) per `Appointment` | OK |
| Book Appointment `<<extend>>` Send Reminder | `AppointmentReminder` is optional (0..*) per `Appointment` | OK |
| View Dashboard `<<extend>>` Generate Report | `Report` is a separate class requested by `ClinicStaff` | OK |

## 4. DFD processes and data stores to classes

| DFD element | Classes | Result |
|---|---|---|
| P1 Manage Accounts and Access | `User`, `Role`, `Patient`, `Nurse`, `ClinicStaff` | OK |
| P2 Manage Appointments and Waitlist | `AppointmentSlot`, `Appointment`, `Waitlist`, `Cancellation` | OK |
| P3 Verify Eligibility and Administer Dose | `Nurse`, `EligibilityChecker`, `VaccinationDose`, `Contraindication`, `Deferral`, `AdverseReaction` | OK |
| P4 Track Follow-up and Flag Overdue Doses | `OverdueFlag`, `ClinicStaff`, `Vaccine` | OK |
| P5 Send Reminders and Notifications | `Notification`, `AppointmentReminder`, `OverdueReminder` | OK |
| P6 Provide Dashboard, History and Reports | `Dashboard`, `Report`, `Patient.viewHistory()` | OK |
| D1 Users and Roles | `User`, `Role`, `Patient`, `Nurse`, `ClinicStaff` | OK |
| D2 Appointments and Waitlist | `Appointment`, `AppointmentSlot`, `Waitlist`, `Cancellation` (cancelled part) | Gap (issue 3) |
| D3 Vaccination Records | `VaccinationDose`, `Contraindication`, `Deferral`, `AdverseReaction`, `OverdueFlag`, missed-visit record | Gap (issue 3) |
| D4 Vaccine Schedule Reference | `Vaccine` | OK |

`EligibilityChecker`, `Dashboard` and `Report` hold logic or derived views and need no data store of their own. `Notification` has no data store in the Level-0 DFD, see issue 6.

## 5. Relationships and multiplicities

**Inheritance** (each is a genuine generalization): `Patient`, `Nurse`, `ClinicStaff` extend `User`; `AppointmentReminder`, `OverdueReminder` extend `Notification`. Result: OK.

| Association | Name | Multiplicity | Check | Result |
|---|---|---|---|---|
| Role - User | has role | 1 : 0..* | Each user has exactly one role | OK |
| ClinicStaff - Dashboard | views | 1 : 0..* | A staff member opens many dashboards | OK |
| ClinicStaff - Report | requests | 1 : 0..* | A staff member generates many reports | OK |
| ClinicStaff - OverdueFlag | overrides | 0..1 : 0..* | A flag is overridden by at most one staff member | OK |
| Dashboard - Appointment | summarizes | 0..* : 0..* | Views overlap on appointments | OK |
| Report - Patient | lists overdue | 0..* : 0..* | Many patients per report, a patient in many reports | OK |
| Patient - Appointment | books | 1 : 0..* | Each appointment belongs to one patient | OK |
| Patient - Waitlist | waits on | 0..* {ordered} : 0..* | Queue order matters (FR-05) | OK |
| Patient - OverdueFlag | flagged | 1 : 0..* | One patient, many flags over time | OK |
| Patient - Notification | receives | 1 : 0..* | One patient, many notifications | OK |
| Patient - Contraindication | has | 1 : 0..* | One patient, many recorded conditions | OK |
| Patient - VaccinationDose | receives | 1 : 0..* | One patient, many doses | OK (duplicate label, issue 6) |
| Nurse - VaccinationDose | administers | 1 : 0..* | One nurse, many doses | OK |
| Appointment - AppointmentSlot | occupies | 0..* : 1 | A slot has capacity for many appointments | OK |
| Appointment - Cancellation | cancelled | 1 : 0..1 | At most one cancellation per appointment | OK |
| Appointment - VaccinationDose | has administered | 1 : 0..1 | One dose per completed visit | OK |
| Appointment - Deferral | deferred by | 1 : 0..* | A visit can be deferred more than once | OK |
| Appointment - AppointmentReminder | reminds of | 1 : 0..* | Reminders are optional | OK |
| AppointmentSlot - Waitlist | queued | 1 : 0..1 | One waitlist per full slot | OK |
| Vaccine - AppointmentSlot | offers | 1 : 0..* | A slot is for exactly one vaccine | OK |
| Cancellation - AppointmentSlot | releases | 0..* : 1 | Each cancellation releases one slot | OK |
| Vaccine - OverdueFlag | overdue for | 1 : 0..* | A flag is raised for one vaccine | OK |
| OverdueFlag - OverdueReminder | reminded by | 1 : 0..1 | At most one pending reminder per flag | OK |
| VaccinationDose - Vaccine | of | 0..* : 1 | Each dose is of one vaccine | OK |
| VaccinationDose - AdverseReaction | has recorded reaction | 1 : 0..* | A reaction links to one dose | OK |
| Contraindication - Vaccine | affects | 0..* : 1..* | A condition affects at least one vaccine | OK |

**Dependencies:** `ClinicStaff` assigns `Role`; `Cancellation` triggers a check on `Waitlist`; `Waitlist` alerts `Notification`; `EligibilityChecker` checks `Contraindication`, uses `VaccinationDose` history, and uses `Vaccine` for the schedule. Result: OK.

## 6. Issues found

1. **ClinicStaff lacks operations for UC-01 and UC-05.** The inventory lists both, but the class only has `assignRole`, `revokeRole`, `viewDashboard` and `generateReport`. Add a method for reviewing or overriding a flag and one for marking a no-show.
2. **No cancel or join-waitlist operation on Patient or Appointment.** `Patient` and `Appointment` are linked to UC-02 and UC-03, but only `Cancellation.releaseSlot()` and `Waitlist.join()` exist. The team needs to decide which class owns "cancel" and keep the inventory consistent.
3. **Cancellation straddles D2 and D3.** It covers cancelled and missed appointments, but the Core Processes Matrix stores cancellations in D2 and missed visits in D3. Cancellation also has no attribute that distinguishes the two. Add a type attribute, or split the missed visit into its own record.
4. **FR-02 names Clinic Staff, but the model uses Nurse.** FR-02 says clinic staff record administered doses, while FR-11 and FR-12 and the class model use the nurse. Update FR-02 or note the change.
5. **Role management actor.** FR-19 and FR-20 say System Admin, while UC-18, the Lab 4 matrix and the class model say Clinic Staff. Update the FR wording to match.
6. **Diagram cleanup.**
   - `Notification` has no data store in the DFD, so decide whether notifications are persisted (NFR-18 asks for failed deliveries to be logged).
   - Two associations from `Patient` are both labeled "receives".
   - Some note connectors are unattached.
   - Narrow classes clip their text.
