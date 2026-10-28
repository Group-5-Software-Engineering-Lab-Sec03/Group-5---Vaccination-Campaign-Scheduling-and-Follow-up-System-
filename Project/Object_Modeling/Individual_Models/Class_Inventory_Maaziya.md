# Individual Class Inventory

**Student:** Maaziya (g00099913)
**Component:** Patient accounts and booking

| Class ID | Class Name | Purpose / Responsibility | Related Use Case(s) | Contributor |
|---|---|---|---|---|
| C09 | User | The main account class for everyone who logs in (patient, nurse, clinic staff). It stores the login details and the user's role. | UC-06, UC-18 | Maaziya |
| C10 | Patient | A type of User. A patient can register, search for slots, book or reschedule an appointment, and view their vaccination history. | UC-06, UC-07, UC-08, UC-09, UC-10 | Maaziya |
| C11 | Appointment | One booked dose visit. It keeps the status of the visit (booked, cancelled, completed, etc.) and can be moved to a new slot. After the visit, it links to the dose that was given. | UC-08, UC-09, UC-10 | Maaziya |
| C12 | AppointmentSlot | A time slot that a patient can book for a vaccine. It checks if the slot is still free and is marked as booked or released. | UC-07, UC-08, UC-09 | Maaziya |
| C14 | Vaccine | Stores the facts about each vaccine: how many doses it needs, the gap between doses, and whether a booster is needed. | UC-07, UC-08 | Maaziya |

**Note on AI tool use (Claude):** This document was drafted with the assistance of an AI tool (Claude) to help with the structure and to format the content into proper Markdown table syntax, so that it displays correctly as a table when viewed on GitHub or in Markdown preview mode.
