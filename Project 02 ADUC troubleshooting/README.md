Project 02.5 – ADUC Troubleshooting

Tasks Covered
- User Password Resetting
- Practiced resetting passwords for locked‑out users in ADUC.
- Verified login with new credentials.
- Documented the process and security considerations.
- Inheritance & Cleanup
- Encountered inherited NTFS permissions blocking direct removal of a user.
- Disabled inheritance, converted entries to explicit permissions, and cleaned up access lists.
- Learned how permission flow works between parent and child objects.
- Trust Relationship Errors
- Experienced “The security database on the server does not have a computer account for this workstation trust relationship.”
- Fixed by rejoining the domain or resetting the computer account in ADUC.
- Documented the secure channel concept between DCs and member servers.
- OU Moves & Policy Impact
- Moved computer objects between OUs and observed changes in applied Group Policies.
- Learned that OU placement isn’t cosmetic — it directly affects security and configuration.

Topology Environment
- ADUC showing password reset dialog.
- NTFS Advanced Security Settings (inheritance disabled).
- Trust relationship error message and resolution steps.
- OU structure before/after moving computer objects.

Lessons Learned
- Password resets are a core ADUC task and must be documented for audit/security.
- NTFS inheritance can block direct edits; disabling inheritance is required for cleanup.
- Trust relationships are critical — broken secure channels prevent even Domain Admins from logging in.
- OU placement determines which GPOs apply, so structure must be planned carefully.
- Troubleshooting teaches why things break, not just how to configure them.



