# Purpose
When an eligible Neo disk-capacity Problem ticket reaches a completed status, complete only its single, correctly linked originating disk-alert ticket.

# Mandatory eligibility gate
At the start of every run, read the triggering Problem ticket directly from Autotask and stop without making changes unless all conditions below are true:
1. Its ticket type is Problem.
2. Its title contains `[NEO] Disk Capacity`.
3. Its current status is exactly `Complete` or `Completed (With CSAT)`. A callback alone is not enough; a reopened or otherwise non-completed Problem ticket must never close an alert.

# Resolve exactly one originating alert
Find the originating alert reference only from the established cross-link on the completed Problem ticket:
- Prefer `Originating alert ticket: T...` in the Problem description.
- Otherwise accept `Triggered by alert ticket T...` in an internal Problem-ticket note.
Do not infer an alert from matching company, device, volume, title, or recent history. If zero references, more than one different reference, or an unreadable/nonexistent reference is found, stop without making changes.

# Required cross-checks
Read the referenced alert ticket and stop without making changes unless all conditions below are true:
1. The alert belongs to the same Autotask company as the completed Problem ticket.
2. The alert contains a cross-link to this Problem ticket, such as `Escalated to capacity problem ticket T...`, in its internal notes or description.
3. The alert is not already in `Complete` or `Completed (With CSAT)`.

# Only permitted write
When every gate and cross-check passes, update only the linked alert ticket's status to `Complete` (Autotask status ID 5). Add one internal note to that alert:
`Closed automatically because linked capacity Problem ticket <Problem ticket number> is complete.`

# Safety and idempotency
- Do not create, modify, reclassify, assign, or add notes to any Problem ticket.
- Do not create tickets, Problem tickets, RMM jobs, schedules, time entries, client-facing notes, emails, Teams messages, or workflow triggers.
- Do not change any alert field except the qualifying originating alert's status.
- If the alert is already complete, do nothing and add no duplicate note.
- If any validation is inconclusive or fails, do nothing and add no note anywhere.
- Do not close an alert because an unrelated Problem ticket is complete.
