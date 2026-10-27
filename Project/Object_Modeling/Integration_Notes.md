# Integration Notes

Group 5 - Vaccination Campaign Scheduling and Follow-up System

These notes explain what we changed when we merged our four individual class diagrams into one. The final list of classes is in `Class_Inventory.md` (21 classes), and the final diagram is in `Class_Diagram/`.

## Who did what

| Member | ID | Classes |
|---|---|---|
| Saif Almas | b00100949 | OverdueFlag, Waitlist, Cancellation |
| Sara | g00101461 | VaccinationDose, EligibilityChecker, Contraindication, Deferral, AdverseReaction |
| Maaziya | g00099913 | User, Patient, Appointment, AppointmentSlot, Vaccine |
| Muhammad Ahmed Raza | b00100977 | Notification, AppointmentReminder, OverdueReminder, Role, ClinicStaff, Dashboard, Report |

## Classes that appeared in more than one diagram

Most of us drew User, Patient and Appointment because they connect to everything else. We kept one version of each:

- **User**: one abstract class. We used `fullName` instead of `name` and kept `passwordHash` and the login/logout methods.
- **Patient**: combined everyone's version into one class, with the booking methods from Maaziya's diagram.
- **Appointment**: kept Maaziya's attributes and added `markCompleted()` and `markDeferred()` from Sara's diagram.
- **AppointmentSlot, Waitlist, Cancellation, VaccinationDose, OverdueFlag, ClinicStaff, Notification**: some of us only drew these as small boxes to link to our own classes. We kept the full version from the person who owns the class.

## Changes we made

1. **Role replaces the `role` String on User.** Staff need to assign and change permissions (FR-19, FR-20), and a String cannot hold permissions.
2. **VaccineSchedule was merged into Vaccine.** It had the same data (total doses and the gap between doses). `getRequiredInterval()` now lives in Vaccine, and EligibilityChecker uses Vaccine.
3. **Vaccine fields that were Strings are now links to Vaccine.** This applies to VaccinationDose, OverdueFlag and Contraindication, so the vaccine data is stored in one place.
4. **Method parameters use real classes.** For example, `checkEligibility(patient: Patient, vaccine: Vaccine)` instead of `v: String`.
5. **Nurse got methods.** It only had `nurseId` before. We added `administerDose`, `verifyEligibility`, `recordContraindication`, `deferDose` and `reportReaction` to match UC-11 to UC-15.
6. **Inheritance only where it makes sense.** Patient, Nurse and ClinicStaff extend User. AppointmentReminder and OverdueReminder extend Notification.

## Things we dropped

- Sara's note about requesting a next-dose reminder after a dose is given.
- Saif's direct "cancelReminder" link from OverdueFlag to Notification. The same thing now happens through `cancelPendingReminder()` and the link between OverdueReminder and OverdueFlag.

**Note on AI tool use (Claude):** This document was drafted with the assistance of an AI tool (Claude) to help with the structure and to format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.
