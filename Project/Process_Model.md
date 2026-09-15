# Process Model — Vaccination Campaign Scheduling and Follow-up System

For Exercise 1: Lab 2.

## 1. Selected Software Process Model

**Incremental Model**

## 2. Justification

**Our system splits naturally into a core and add-ons.** Our system splits naturally into three parts: booking, record-tracking, and the missed-dose flagging engine. We can build booking as the "core" first, then add record-tracking and flagging as later increments, this is exactly how the Incremental Model works.

**Our scope already changed once.** We started with one fixed vaccination program and broadened it to general vaccination campaigns. With increments, we don't need to lock in every requirement at the start, we can build the basic version first and add flexibility (multiple vaccines, custom dosing) later.

**We have a fixed, short deadline.** Since the course only runs one semester, we need something working early, not just at the end. Each increment gives us a version we can actually test against our timeline, and if we run low on time we can just skip or delay a later increment instead of finishing with nothing done.

**It makes the workload easier to manage.** Since we also have other courses, exams, and deadlines, dividing the project into smaller increments makes the workload easier to organize. Instead of trying to complete the entire system at once, we can focus on a smaller set of features at each stage.

**We need early feedback from real users.** Patients and staff are the ones who will actually use this system, so we need to know early on if the booking flow or the flagging results make sense to them, not just find out at the very end. Since each increment is a working version, we can demo it to a few real users and adjust based on what they say before building the next part.

**It lowers integration risk.** We're building three connected modules: booking, record-tracking, and flagging that all depend on the same appointment and patient data. If we tried to build all three separately and only connect them at the end, small mismatches in how the data is structured could turn into big problems all at once. Building and testing one increment at a time means we connect and check each piece as we go, so issues get caught early instead of piling up for a single stressful integration at the end.

Compared to alternatives: **Waterfall** doesn't handle change well and tests too late to catch issues early, which doesn't fit our evolving scope. **Scrum** needs more meetings and roles (daily stand-ups, sprint planning, a Product Owner) than a small student team can realistically keep up, though we borrow its spirit of short cycles and working software. The **Spiral Model** is built for large, high-risk projects with dedicated risk-assessment work, which is more than our project needs, we handle risk through our own Risk Register (Exercise 3) instead.

## 3. Major Overheads/Drawbacks and How We Will Manage Them

| Overhead / Drawback | Why it applies to our project | How we will manage it |
|---|---|---|
| **Each increment requires separate planning and testing** | Since we are developing the system in parts, each new increment needs to be planned and tested before moving to the next one. | We will clearly decide what features belong to each increment and test them as they are completed. |
| **Later increments may require changes to earlier ones** | For example, adding multiple vaccine types later may require changes to the booking or record-tracking features developed earlier. | We will keep the system flexible and review upcoming features before completing each increment so that major changes can be reduced. |
| **Integration problems may happen between increments** | Booking, record-tracking, and missed-dose flagging all use related patient and vaccination information, so the parts need to work correctly together. | We will test the connection between the features whenever a new increment is added instead of waiting until the whole system is finished. |
| **There is a risk of adding too many features** | Because the Incremental Model makes it easy to keep adding features, our project could become too large for one semester. | We will give priority to the main features first, such as booking, record-tracking, and missed-dose flagging. Extra features will only be added if enough time remains. |
| **The complete system is not available immediately** | Users will only have some features in the early increments, while other functions are still being developed. | We will make sure the first increment already provides useful core functionality, then gradually add the remaining features. |

---
*Note on AI tool use: This document was drafted with the assistance of an AI tool (Claude) to structure the process-model justification and format it as Markdown, consistent with the rest of the Lab 2 artifacts.*
