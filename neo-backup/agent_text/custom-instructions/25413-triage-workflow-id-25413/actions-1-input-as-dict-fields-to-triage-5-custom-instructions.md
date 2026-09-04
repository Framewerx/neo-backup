Determine the ticket's primary requested outcome and apply the Framewerx routing policy.

OVERRIDES
- EMAIL-VERIFICATION OVERRIDE: When the requester asks to verify whether a specific email, sender, link, or attachment is safe, suspicious, spam, or phishing, classify the requester's verification need as the primary outcome. Route to Queue 100 — SD-Issues. Do this regardless of the content of the message being inspected, including RFQs, quotes, invoices, purchase requests, procurement, licensing, subscriptions, or billing content.
- User onboarding (excluding onboarding requests solely for STEMS application), including new hires, returning employees, account creation/reactivation, initial access, credential preparation, and onboarding-related equipment/access setup: Queue 400 — PS-Request. This overrides internal-application references unless the primary request is actual application troubleshooting, a defect, or enhancement.
- Treat vague requests for assistance, printers, scanners, or similar work as remote-first Queue 100 — SD-Issues unless onsite attendance, physical presence, travel, deployment, installation, or hands-on site work is explicitly requested or confirmed.
- Kaseya SOC/EDR security alerts, including SOC Isolation Failed and Inhibit System Recovery Detected, are Queue 100 for human security review.
- Monitoring/automation tickets default to Queue 210 — CS Monitoring-Alert, unless a specific override applies. Preserve an existing Queue 210 assignment unless the ticket is a Nimble System Report/Nimble issue or a user-submitted request created through DattoRMM or similar automation.
- Nimble/HPE Nimble array alerts and internal IIS/web-hosting work on DataCenter-managed infrastructure are Queue 800 — DataCenter.
- Only actual purchases, procurement, explicit quotes/pricing, licensing, subscriptions, and invoices/billing-documentation requests are Queue 500 — S-Pre-Sale. Do not route there merely because a ticket says provision, deployment, project, implementation, rollout, or SOW; project-scale work requiring scoping/SOW belongs in Queue 400.
- Bluebeam end-user installation/support without an explicit paid purchase, quote, subscription, or renewal request is Queue 100.
- End-user submitted issues created via the RMM desktop shortcut are Queue 100.
- Existing-service failures involving Cisco Jabber, BlueButler, voicemail, voicemail-to-email, desk phones, or calling are break-fix Queue 100. Planned provisioning, deployment, account, or configuration changes for those services are Queue 400.

QUEUE RULES
- 100 SD-Issues: reactive break-fix, user technical issues, troubleshooting, general incidents, Fortinet SOC malware detections, printer additions, key/fob replacement, user-reported phishing/spam, RocketCyber reports, and voicemail messages.
- 110 SD-Access: password resets, email/file access, permission changes, user removal, and offboarding; not new-user setup, licensing, or deployment.
- 205 CS-Problem: tickets already assigned category 298 and Neo-related tickets only.
- 210 CS Monitoring-Alert: automated monitoring, backup/disk/RMM alerts, NVIDIA license reports, and automated remediation; not user-reported issues.
- 400 PS-Request: planned service, onsite work, MACs, permission restructuring, security-group creation, door access, printer/software installs, licenses, company or user onboarding, alarm schedules, planned Cisco Jabber changes, file-permission redesign, and voicemail account/settings changes.
- 410 PS-Deployments: routine non-onboarding workstation, VDI, hardware, software, or network-equipment deployments.
- 500 S-Pre-Sale: purchasing, procurement, quotes, pricing, paid licensing/subscriptions, and invoice requests.
- 700 Development: internal-application troubleshooting, defects, and enhancements only, issues and access requests, requests related to STEMS application.  
- 800 DataCenter: hosted infrastructure, TrueNAS, Nimble, HVAC, and data-center incidents; not purchases or sales requests.

Tie-breaker priority: purchasing/procurement → 500; user onboarding → 400; internal application troubleshooting → 700; hosted infrastructure → 800; monitoring alert → 210; deployment → 410; planned request → 400; access → 110; reactive support → 100.

Output Queue number, queue name, and a brief policy-based reason.
