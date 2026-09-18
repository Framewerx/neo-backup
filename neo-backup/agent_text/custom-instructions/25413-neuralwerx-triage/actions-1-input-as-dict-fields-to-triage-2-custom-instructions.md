- Treat adding or modifying mailbox delegation as break-fix.


# 400 Add/Move/Change work type assignment.  

Assign Work-Type "400 Add/Move/Change" if the ticket matches any of the following definitions: 
		
	ADD -  Work where we introduce something that did not exist before for that user, location, or environment.
				Typical examples:
					- New user onboarding (new account, mailbox, licenses, security groups).
					- New device (workstation, printer, phone, server, network device).
					- New service or resource (new shared mailbox, new file share, new VPN profile, new line-of-business app instance).
					- Adding a new license or feature that wasn’t present before.
			rule of thumb: If the request’s main outcome is “there is now an extra thing,” classify as Add.
			
	MOVE - Work where an existing asset/service is reassigned or relocated, but largely remains the same service.
				Typical examples:
					- Moving a user from one workstation to another and reassigning profiles/settings.
					- Moving a phone/extension or physical workstation to a different desk, office, or site.
					- Moving an existing mailbox, shared folder, or group ownership to another user or team.
					- Moving network drops or patching an existing port to a new location.
			rule of thumb: If the main work is “same thing, different user/location,” classify as Move.

	CHANGE  - Work where an existing asset/service is modified, without being primarily a relocation or a net-new addition.
				Typical examples:
					- Permissions changes (file share, mailbox, app access), group membership changes.
					- License changes (upgrading/downgrading plans, changing SKUs without adding a net-new user).
					- Configuration changes (security policies, firewall rules, routing rules, backup schedules).
					- Capacity/feature changes (increasing mailbox size, enabling MFA, changing retention, adjusting alerts).
			rule of thumb: If the main outcome is “same thing, but configured differently,” classify as Change.
	
Tie-Breaking Logic:  

   * Add vs Change: If there is a clear net-new asset/service (new user, new device, new shared resource), route as Add, even if it includes config changes.
   * Move vs Change: If the key impact to the user is relocation/reassignment, route as Move; otherwise treat pure configuration/permissions work as Change.
