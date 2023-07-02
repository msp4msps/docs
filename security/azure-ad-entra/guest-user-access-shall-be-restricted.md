# Guest User Access Shall be restricted

## Description

Ensure that only users with specific privileges can invite guest users to the tenant and that invites can only be sent to specific external domains. Ensure that guest users have limited access to Azure AD directory objects and that they are required to use MFA.

## Policy

* Only users with the Guest Inviter role should be able to invite guest users.
* Guest invites should only be allowed to specific external domains that have been authorized by the agency for legitimate business purposes.
* Guest users should have limited access to Azure AD directory objects
* Guest users shall use MFA
* Guest User Access is periodically reviewed

## Licensing Considerations

All License models support the guest settings. Azure AD P1 is required to enforce MFA for Guest users via Conditional Access Can be purchased standalone or part of the following bundles:

* Microsoft 365 Business Premium
* EMS+ E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

1. Configure guest settings in the portal: [Enable B2B external collaboration settings - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/external-collaboration-settings-configure#configure-settings-in-the-portal)
2. Under Guest user access, select Guest users **have limited access to properties and memberships of directory objects**
3. Under Guest invite settings, select **Only users assigned to specific admin roles can invite guest users**
4. Under Collaboration restrictions, select **Allow invitations only to the specified domains** (most restrictive). Select Target domains and enter the names of the external domains that have been authorized by the agency for guest user access.
5. Create a Conditional Access Policy with the [Templates available](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common#conditional-access-templates-preview)
6. Chose the “Require Multi-Factor authentication for guest access” setting
7. Leverage the sign-in logs to review guest user access

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

Users will not be able to invite guest users to the organization without the Guest Inviter role. A formal process should be put into place to request guest access for certain organizations or users.

{% hint style="info" %}
Tips

Use the collaboration settings for external users who are not using Azure AD.&#x20;

Use [cross-tenant access settings](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect) for external users in another Azure AD environment.
{% endhint %}

## PowerShell Scripts

Assign User as Guest Inviter: [Enable B2B external collaboration settings - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/external-collaboration-settings-configure#assign-the-guest-inviter-role-to-a-user)

Allow or Block Domains: [Allow or block invites to specific organizations - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/external-identities/allow-deny-list#set-the-allow-or-blocklist-policy-using-powershell)

## Videos

{% embed url="https://www.youtube.com/watch?v=ON0QQKkGGTo" %}

{% embed url="https://www.youtube.com/watch?v=Ku64fo7iZ4Y" %}

{% embed url="https://www.youtube.com/watch?v=9P10hgPDRZg" %}
