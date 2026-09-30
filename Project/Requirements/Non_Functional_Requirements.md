| NFR ID | Category | Non-Functional Requirement | Contributor |
|---|---|---|---|
| NFR-01 | Reliability | The automatic flagging for missed dose logic shall produce a false positive rate of less than 5% when tested against a sample set of at least 100 previous appointment records. | [Saif Almas] |

**Note on AI tool use (Claude):** This non-functional requirement was drafted with the assistance of an AI tool (Claude) to help with the structure and format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.


## Sara Alhammadi (g00101461) Contributions

| NFR ID | Category | Non-Functional Requirement | Contributor |
|---|---|---|---|
| NFR-11 | Usability | A nurse shall be able to complete the full dose-administration and recording workflow for one patient in 3 screens or fewer during a clinic visit. | Sara |
| NFR-12 | Reliability | Dose administration records shall be saved to the patient's history with at least 99.9% write success, and the system shall locally cache an entry and retry submission if network connectivity is temporarily lost mid-visit. | Sara |
| NFR-13 | Portability | The nurse workflow shall be fully usable on tablets with a screen of 10 inches or larger, and in the latest two versions of Chrome, Edge, and Safari, without loss of functionality. | Sara |
| NFR-14 | Performance | The system shall display a patient's profile, vaccination history, and eligibility result to the nurse within 3 seconds of selecting the patient, for 95% of requests under normal load. | Sara |
| NFR-15 | Security | A nurse's session shall log out automatically after 10 minutes of inactivity, so patient records are not left open on shared clinic devices. | Sara |


## Maaziya Contributions

| NFR ID | Category | Non-Functional Requirement | Contributor |
|---|---|---|---|
| NFR-06 | Usability | A patient shall be able to complete a full appointment booking in no more than 4 steps from login. | Maaziya |
| NFR-07 | Performance | Appointment slot search results shall load within 2 seconds under normal load. | Maaziya |
| NFR-08 | Security | All patient account data and booking information shall be transmitted using encrypted connections. | Maaziya |
| NFR-09 | Reliability | Appointment booking confirmations shall succeed at a rate of at least 99% under normal system operation. | Maaziya |
| NFR-10 | Scalability | The booking system shall support at least 200 concurrent active users without performance degradation. | Maaziya |

## Ahmed Contributions

| NFR ID | Category | Non-Functional Requirement | Contributor |
|---|---|---|---|
| NFR-16 | Usability | The clinic staff dashboard should display the full appointment summary for the day on the whole screen without having to scroll, for up to 20 appointments. | Ahmed |
| NFR-17 | Security | The system should only allow role-based access so patients can only view their own records and staff can only access records for patients assigned to them. | Ahmed |
| NFR-18 | Reliability | Reminder notifications shall be delivered successfully to at least 98% of recipients, with failed deliveries logged and automatically retried once within 24 hours. | Ahmed |
| NFR-19 | Performance | The system should be able to generate a report covering up to 3 months of data, completing within 5–15 seconds. | Ahmed |
| NFR-20 | Maintainability | The administrator should be able to update and change user role permissions without requiring a system restart or code deployment, with changes reflected within hours. | Ahmed |
