# Initial Feasibility Study - Vaccination Campaign Scheduling and Follow-up System
Conduct an initial feasibility study for your proposed project.
Your study should briefly evaluate the following:


1	A. Technical Feasibility
Can the system be developed using the technologies, tools, hardware, software, and technical skills available to the team?
The system that we have proposed can in actuality, be built for our real life use case using standard web development technologies that we have learnt over the four years at university, such as using standard databases for record keeping, front-end, back-end, and overall API development strategies. The main technical challenge would be the logic of the missed dose flagging, as it depends on correctly modelling different vaccine dosing intervals. 

2	Economic Feasibility
Are the expected costs and resources reasonable for the proposed project? Identify any expected costs, required resources, or limitations.
There should be no visible high end costs, as the methods and the technologies that we will be using for hosting, database, and development tools are all open sourced and free. However, since we are handling sensitive patient data, and this could be in large numbers, the addition of security measures for our project could incur costs, as we could require HTTPS certificates that are beyond what our general host will provide and could cost. Furthermore, if we wish to make the process for the reminders to patients smooth, we’ll have to invest in automated Gmail messaging, or, like recent hospitals have done, through SMS reminders, which cost per message that is sent.


3	Operational Feasibility
Is the proposed system expected to solve a real problem or meet a genuine user need? Are the intended users likely to use and accept the system?
Our proposed system addresses a real world problem, and this is backed by the AHRQ reference provided earlier in the Scope section. Our proposed users, which are most likely the clinic staff, are likely to work using our system because it reduces manual labour in record keeping and patients are also likely to use it because it helps them save time and is a general low effort alternative to manually scheduling appointments.


4	Schedule Feasibility
Can the major project features and deliverables realistically be completed within the available course duration?
Given our one semester timeline, the incremental model that we have chosen supports the scheduling feasibility directly, and we can do them as follows:
-we can do the fundamental booking feature as a working increment early on
- we can then add the record tracking and flagging as we move on throughout the semester
-the multi-vaccine flexibility can be added smoothly as well, but it can be scaled back should time in the semester run short.
Overall, we plan to commit to the completion of the system in the timeframe of the semester and hope to fulfill all requirements necessary for the project.


5	Overall Feasibility
Based on the above analysis, provide a brief conclusion stating whether the project appears feasible and identify any major constraints that may affect its successful completion. Ultimately, we are keen on the fact that our project seems feasible within the timeframe of the semester and we are also reliant on the technical skill sets of our team. The main constraints that we could face are, as mentioned above:
-keeping the dosing vaccine model flexible enough for general campaigns without over engineering it early.
- keeping the sensitive health data appropriately and securely (R2).
-managing schedule risk from the already wide scope (R7).
While none of these are  particularly blocking as they all have mitigation strategies already defined in the Risk Register so the team will proceed with the Incremental Model as planned, prioritizing the booking increment first.
Note on AI tool usage: the costs that could be incurred by the security measures and messaging systems were thought through the assistance of AI in specific “Claude”.
