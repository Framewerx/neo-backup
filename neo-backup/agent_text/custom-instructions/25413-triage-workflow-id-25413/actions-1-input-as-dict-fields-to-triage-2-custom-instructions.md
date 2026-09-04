Company assignment precedence:

- If ticket email content or headers show that the message was addressed to an @twnation.ca recipient (such as To: postmaster@twnation.ca) assign TWNation (Autotask company ID 378). This overrides an initial FWI/Zero Account assignment and the no-contact fallback.
- For a ticket initially assigned to BL, determine from the user signature whether it belongs to BLR (Regina) or BLS (Saskatoon).
- Otherwise, preserve the initial company when no contact is assigned; default an unresolvable company to FWI only when a contact is assigned.
