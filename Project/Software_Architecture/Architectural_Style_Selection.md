# Architectural Style Selection - Lab 8, Exercise 2

Group 5, Vaccination Campaign Scheduling and Follow-up System.

Team members: Saif Almas (b00100949), Fathimamaaziya Mansoor (g00099913), Sara Alhammadi (g00101461), Muhammad Ahmed Raza (b00100977).

## Selected style

| Layer | Components |
|---|---|
| Layer 3 | CO3 Clinical Care, CO5 Follow-up and Reporting |
| Layer 2 | CO2 Appointment Scheduling |
| Layer 1 | CO1 Access Management, CO4 Notification and Reminders |

## Main characteristics

- Each layer provides services to the layers above it and uses only services of lower layers.
- Components talk only through interfaces (provided and required), so a component's classes stay hidden behind its interface.
- Lower layers do not know the layers above them.
- A layer can hold several independent partitions. Layer 1 has two (CO1 and CO4) and Layer 3 has two (CO3 and CO5).
- In an open layered style a component may use any lower layer directly. CO3 uses CO1 and CO4 without going through CO2.

## Why it is appropriate for the project

- The Lab 5 classes already group by purpose: accounts, scheduling, clinical care, notifications, and follow-up. These groups depend on each other in one direction. Scheduling and clinical care both need accounts and notifications, and nothing in the account or notification groups needs scheduling or clinical care.
- The system serves one clinic, so a single deployable system with clear internal layers is enough. A distributed style would add complexity the project does not need.
- Each component can be built and tested separately by a different team member, because the interfaces are fixed in Exercise 4.

## How it supports the design goals

| Goal | How the layered style supports it |
|---|---|
| G1 Reliability | The flagging logic (CO5), the waitlist order (CO2) and the delivery retry (CO4) are each in one component, so each can be tested on its own. |
| G2 Performance | Slot search and booking stay inside CO2. The open style lets CO3 call CO1 and CO4 directly, which avoids extra hops. |
| G3 Security | All access checks are in CO1, in the lowest layer, and every other component uses its interfaces. Access control is implemented in one module only. |
| G4 Scalability | CO2 gets the most traffic during a vaccination campaign and can be improved or scaled without changing the other components. |
| G5 Availability | The local caching and retry of dose records is inside CO3, so a network drop during a visit affects only that component. |
| G6 Usability | CO3 exposes a few complete operations (check eligibility, record the dose) through its interfaces, so the nurse workflow needs few screens. |

## Advantages

- Low coupling: components depend only on interfaces of lower layers.
- A component can be replaced or improved without changing the layers above it.
- The dependency direction is easy to check, since no component may call upward.
- Components can be developed in parallel.

## Potential limitations

- Calls that pass through interfaces add some overhead. This is acceptable for a one-clinic system.
- CO2 has many classes, so its interfaces must be kept small and stable.
- The open style weakens strict isolation. A change to CO1 or CO4 can affect several layers above it.
- The user classes Patient, Nurse and ClinicStaff are in CO1 but their operations (book, administer a dose, review a flag) use higher layers. These actions are carried out through the interfaces of CO2, CO3 and CO5, called by the user interface, so CO1 itself does not call upward.

**Note on AI tool use (Claude):** An AI tool (Claude) was used to help draft this document and format it into Markdown. 