Ticket Category should typically follow queue assignment decided in this triage action (example: 100 queue means 100 ticket category, 210 queue means 210 category and so on...)

Exceptions: 
- Tickets assigned to 800 queue should have ticket category 100 
- If the ticket already has 210 ticketCategory assigned, preserve the existing ticketCategory  
    Unless: Ticket is user submitted request & created by DattoRMM API (or similar)
    Unless: Ticket is HVAC monitoring or Nimble Storage Alert
- Requests for invoices or billing documentation (e.g., invoice copy/details, attach vendor invoice) MUST be directed to Sales Team — assign ticketCategory 500.
- End-user submitted issues via the RMM desktop shortcut (Created by: DattoRMM API but end-user originated) — assign ticketCategory 100.
