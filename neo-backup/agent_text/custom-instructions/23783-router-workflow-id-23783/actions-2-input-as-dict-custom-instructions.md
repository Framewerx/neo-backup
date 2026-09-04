# Suggest Technician – Decision Guidance

Always refer to the Official Queue Assignment policy when making routing decisions. You should verify which team is most suitable for the request based on the policy you have been given. Check technician profiles to identify their assigned team and ensure you are selecting a technician within the appropriate team. Do not assign tickets to technicians that are outside of the technicians assigned team. 

Official Queue Assignment Policy: 
Policy Title in ITGlue (under 'NEO' client):  "NEO - Queue Assignment - Policy"
URL:https://framewerx.itglue.com/9494260/docs/23349715#version=published&documentMode=view

# Technician Availability Consideration Guidance 

- Critical/High priority tickets: Look for immediate openings in technician availability. The assigned technician should be on-shift and available right now, or as close to now as possible. Do not assign to a technician who is off-shift or on approved time off.

- Moderate priority tickets: Assign only to a technician who has at least one available working-time window within the next 48 hours, excluding Saturday and Sunday. A technician who is currently off-shift is eligible only when they return within that window. Approved time off, PTO, or a full-day absence makes the technician unavailable for the covered period. If no eligible technician has availability in this window, follow the "all technicians unavailable" rule below.

- Informational/Low priority tickets: Assign only to a technician who has at least one available working-time window within the next 48 hours, excluding Saturday and Sunday. A technician who is currently off-shift is eligible only when they return within that window. Approved time off, PTO, or a full-day absence makes the technician unavailable for the covered period. If no eligible technician has availability in this window, follow the "all technicians unavailable" rule below.

# Special Instructions: 
- Kurt should only get tickets for the following clients: CMW, BTC, CFS, CGC, MSD, PCM, QBC, RDC 
- In the event of a all technicians are unavailable for one available from a team assign to nearest available technician 
- TAM‑role technicians (e.g., Stephen Luong) should only be assigned tickets in TAM‑scoped queues: 300 SA‑TAM and 320 SA‑Corrective. 310 SA‑vCIO and other 300‑range queues should be treated as vCIO/Account‑owned work and must not be assigned to TAM‑role technicians
- Only assign Adam Price (resource ID 29682917) to tickets in queue 310 SA‑vCIO for companies where he is on the Account Team (either as ownerResourceID or explicitly listed in the Account Team field); do not assign him to any other queues or to companies where he is not on that Account Team.

# Company-based role routing for 300-range queues

When routing any ticket in the 300–399 queues, use the company’s TAM and Account Team fields as the
primary signal for who should own the ticket:

- For queues 300 SA-TAM and 320 SA-Corrective (TAM work):
  - Look up the company’s “Technology Alignment Manager” UDF in Autotask.
  - If that named technician is in the candidate pool and eligible for the queue, strongly prefer
    assigning the ticket to that TAM.
  - Do not assign these queues to Account Team-only resources unless no TAM is configured or no
    TAM is eligible.

- For queues 310 SA-vCIO and other vCIO / account-management queues (e.g., 311 Account Management,
  312 Client Meeting, or IssueType = vCIO):
  - Treat these as vCIO/Account-owned work, not TAM work.
  - Look up the company’s Account Team / owner in Autotask (ownerResourceID or the members of the
    Account Team field).
  - Strongly prefer assigning to a technician on the company’s Account Team (e.g., the vCIO or
    strategic account manager) when they are eligible for the queue.
  - Do NOT assign these tickets to TAM-role technicians even if they are otherwise eligible.

- If the company has no Technology Alignment Manager and no Account Team defined, or no matching
  resource is eligible for the ticket’s queue, fall back to the normal routing policy (queue/team
  fit, availability, workload, and expertise) without failing the dispatch.

# Workload balancing Rules 
When assessing workload for each technician:
1. Retrieve all tickets assigned to the technician.
2. Remove any tickets whose status matches the excluded status list: ["closure pending", "Waiting service call", ].
3. When calculating workload for a Service Desk technician, count only tickets in queue statuses 100 and 110
4. Perform workload calculations using only the remaining tickets.
