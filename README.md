# Reset_MFA_Methods_via_Graph
This powershell script automates removal of users' registered mfa methods

 IMPORTANT
Resetting MFA methods means users will be required to re-register their authentication methods (e.g., Authenticator App, phone number) the next time they sign in. Proceed with care and let your users know what's up.

What It Does
Fetches all authentication methods for each user (including Phone, App, etc.).

Deletes each method — causing MFA reset on next login.

Logs every action, both success and failure, in a timestamped file.

Prerequisites
Install Microsoft Graph module (if not already):

Install-Module Microsoft.Graph -Scope CurrentUser

Make sure your account has permissions:

UserAuthenticationMethod.ReadWrite.All

You can grant it during Connect-MgGraph, or via app registration.

Optional: Just Preview Methods
If you want to preview what you’ll delete, use this:
Get-MgUserAuthenticationMethod -UserId user@domain.com | Select-Object Id, ODataType
