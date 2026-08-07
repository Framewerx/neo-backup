# Suggest Technician – Decision Guidance

Always refer to the Official Queue Assignment policy when making routing decisions. You should verify which team is most suitable for the request based on the policy you have been given. Check technician profiles to identify their assigned team and ensure you are selecting a technician within the appropriate team. Do not assign tickets to technicians that are outside of the technicians assigned team. 

Official Queue Assignment Policy: 
Policy Title in ITGlue (under 'NEO' client):  "NEO - Queue Assignment - Policy"
URL:https://framewerx.itglue.com/9494260/docs/23349715#version=published&documentMode=view

# Technician Availability Consideration Guidance 

- Critical/High priority tickets: Look for immediate openings in technician availability. The assigned technician should be on-shift and available right now, or as close to now as possible. Do not assign to a technician who is off-shift or on approved time off.

- Moderate priority tickets: Immediate (right-now, off-shift) availability does not need to be considered — it is acceptable to assign to a technician who is currently off-shift if they are expected back on their next scheduled work day. However, before assigning, check the technician's calendar/schedule for approved time off, PTO, or other full-day absences covering their next 1-2 scheduled work days. Do not assign to a technician who is confirmed to be off for their entire next scheduled work day — treat them as unavailable and select the next-best eligible technician instead. If every eligible technician on the team is either off-shift with no return within the next scheduled work day, or on approved time off, follow the "all technicians unavailable" rule below.

- Informational/Low priority tickets: Immediate availability does not need to be considered. Assign based on team/queue fit and workload balancing as normal, without checking shift status or near-term time off.

# Special Instructions: 
- Kurt should only get tickets for the following clients: CMW, BTC, CFS, CGC, MSD, PCM, QBC, RDC 
- In the event of a all technicians are unavailable for one available from a team assign to nearest available technician 
- TAM-role technicians (e.g., Stephen Luong) should only be assigned tickets in TAM-scoped queues: 300 SA-TAM, 310 SA-vCIO, 320 SA-Corrective. Never assign a TAM-role technician to any other queue (including 100 SD-Issues, 110 SD-Access, 210 CS-Monitoring Alert, 220 CS-Security, or 610 Merged-Canceled) — this restriction applies even if the technician's PSA resource-role record shows broader queue access. Team/queue fit for TAM technicians is defined strictly by this list, not by their full PSA role record.

# Workload balancing Rules 
When assessing workload for each technician:
1. Retrieve all tickets assigned to the technician.
2. Remove any tickets whose status matches the excluded status list: ["closure pending", "Waiting service call", ].
3. When calculating workload for a Service Desk technician, count only tickets in queue statuses 100 and 110
4. Perform workload calculations using only the remaining tickets.
