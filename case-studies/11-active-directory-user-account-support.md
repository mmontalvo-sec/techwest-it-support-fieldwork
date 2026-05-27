# Case Study 11: Active Directory User Account Support and Help Desk Operations

## Summary

This case study documents hands-on experience with Active Directory user account management tasks common to help desk and desktop support roles. Work covered includes user account creation and configuration, account lockout investigation and resolution, password resets, group membership changes, and account offboarding. This experience was developed through direct Windows Server administration in a lab environment and applied support work in small-office environments running Windows Server with Active Directory.

---

## Environment Note

Active Directory tasks documented here were performed in two contexts: a hands-on Windows Server lab environment configured specifically for learning and practice, and support engagements in small-office settings that operated a Windows Server domain for centralized user management. Both contexts are genuine hands-on experience with real Active Directory and real PowerShell against a live directory service.

---

## Reported Issues (Composite)

This case study covers multiple related help desk scenarios. Each section below documents one category of Active Directory support work.

---

## 1. Account Lockout Investigation and Resolution

### Reported Issue

A user reported being unable to log into their workstation. The error message indicated the account was locked out.

### Diagnostic Steps

| Step | Action | Tool |
|------|--------|------|
| 1 | Confirmed the account was locked out | Active Directory Users and Computers (ADUC) |
| 2 | Reviewed the lockout source | Event Viewer on the domain controller (Event ID 4740) |
| 3 | Identified the workstation triggering repeated failed authentications | Security event log review |
| 4 | Unlocked the account after confirming no malicious activity | ADUC |
| 5 | Advised the user to update saved credentials on the identified workstation | Verbal guidance |

### Common Causes Evaluated

| Cause | How to Check |
|-------|-------------|
| Saved credentials with an old password | Windows Credential Manager on the user's workstations |
| Mapped drive using a cached password | File Explorer mapped drives review |
| Scheduled task running under user credentials | Task Scheduler on the user's machine |
| Mobile device syncing with an outdated password | Direct review with the user |

### Tools Used

| Tool | Purpose |
|------|---------|
| Active Directory Users and Computers | Account status review and unlock |
| Event Viewer (Security log) | Identifying Event ID 4740 for lockout source |
| PowerShell | `Get-ADUser -Identity username -Properties LockedOut, BadLogonCount` |

---

## 2. Password Reset

### Reported Issue

A user was locked out of their account after forgetting their password following a period of leave.

### Work Performed

1. Verified the identity of the requesting user through whatever verification method was available.
2. Reset the password in ADUC to a temporary password meeting the domain complexity policy.
3. Checked the "User must change password at next logon" box.
4. Communicated the temporary password to the user through a secure channel.
5. Confirmed the user successfully logged in and set their own permanent password.

### Tools Used

| Tool | Purpose |
|------|---------|
| Active Directory Users and Computers | Password reset and policy enforcement |
| PowerShell | `Set-ADAccountPassword -Identity username -Reset -NewPassword (Read-Host -AsSecureString)` |

---

## 3. New User Account Creation

### Reported Issue

A new employee needed a domain account configured before their first day.

### Work Performed

1. Created the user account in ADUC under the appropriate organizational unit (OU) for the user's department.
2. Set the account with the username following the site naming convention.
3. Assigned the user to the appropriate security groups for file share access, printer access, and application permissions.
4. Set a temporary password and enforced change at first login.
5. Confirmed the account appeared correctly in the directory before the start date.

### Tools Used

| Tool | Purpose |
|------|---------|
| Active Directory Users and Computers | Account creation and group assignment |
| PowerShell | `New-ADUser` with appropriate parameters |

---

## 4. Account Offboarding

### Reported Issue

A departing employee needed their access revoked promptly following their last day.

### Work Performed

1. Disabled the account immediately (disabled, not deleted, to preserve group membership and mailbox data for the transition period).
2. Removed the account from security groups that controlled resource access.
3. Reset the account password to prevent any reactivation.
4. Moved the account to a disabled accounts OU for retention per policy.
5. Documented the offboarding action and the date.

### Tools Used

| Tool | Purpose |
|------|---------|
| Active Directory Users and Computers | Disable, group removal, OU move |
| PowerShell | `Disable-ADAccount -Identity username` |

---

## 5. Group Membership and Permissions

### Reported Issue

A user reported being unable to access a shared drive that other members of their team could access.

### Diagnostic Steps

1. Confirmed the user could authenticate (not a lockout issue).
2. Checked the shared folder's security permissions to identify which group was granting access.
3. Confirmed the user was not a member of that group.
4. Added the user to the appropriate security group.
5. Advised the user to log off and back on to refresh the group membership token.
6. Confirmed access was restored after re-login.

### Tools Used

| Tool | Purpose |
|------|---------|
| Active Directory Users and Computers | Group membership review and modification |
| File share properties | Security tab review to identify the granting group |
| PowerShell | `Get-ADGroupMember` and `Add-ADGroupMember` |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Account lockout investigation | Event ID 4740 review, lockout source identification |
| Account unlock | ADUC unlock with root-cause communication to the user |
| Password reset | Secure reset with forced change at next logon |
| User account creation | Full user provisioning with OU placement and group assignment |
| Account offboarding | Disable, group strip, OU move, documentation |
| Group membership management | Access troubleshooting through security group review |
| PowerShell for AD | `Get-ADUser`, `Set-ADAccountPassword`, `New-ADUser`, `Disable-ADAccount`, `Add-ADGroupMember` |
| Security event log reading | Event Viewer navigation for lockout event correlation |
| Expectation setting | Each resolution included communication to the user about what was done and what they should do next |

---

## Tools Reference

| Tool | Where to Find It |
|------|-----------------|
| Active Directory Users and Computers | Server Manager or `dsa.msc` on the domain controller |
| Event Viewer (Security log) | `eventvwr.msc` on the domain controller, Windows Logs > Security |
| PowerShell AD module | `Import-Module ActiveDirectory` on a machine with RSAT or on the DC |
| RSAT | Remote Server Administration Tools, installed on a workstation to manage AD remotely |

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Require users to update saved credentials immediately after any password change | Most repeat lockouts come from cached credentials |
| Set a lockout policy with a reasonable threshold | Too low causes legitimate lockouts; too high allows brute-force attempts |
| Document every account action | Offboarding records protect the organization if access issues arise later |
| Use security groups for resource access, not individual user permissions | Makes permission management scalable and auditable |
