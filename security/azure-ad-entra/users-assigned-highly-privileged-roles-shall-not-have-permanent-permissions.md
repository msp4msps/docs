# Users assigned highly privileged roles shall not have permanent permissions

## Description

Do not assign users to highly privileged roles using permanent active role assignments. Instead, assign users to eligible role assignments in a PAM/PIM system and provide an expiration period for active assignments requiring privileged users to reactivate their highly privileged roles upon expiration..

## Policy

* Permanent active role assignments shall not be allowed for highly privileged roles. Active assignments shall have an expiration period.
* The only exception to the policy is the break-glass Global Administrator account.

## Licensing Considerations

Azure AD P2 if using Azure AD PIM. This can be purchased standalone or is part of the following bundles:

* EMS+E5
* Microsoft 365 E5

## Set Up Instructions

Deploy PIM: [Plan a Privileged Identity Management deployment - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-deployment-plan)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Impact is limited to users who are eligible to privileged roles which should be a small amount in the organization. These users will have to enter the Azure AD Admin center to activate their roles when needed.

{% hint style="info" %}
Tips

The emergency break-glass account should be included in the permanent assignments for the Global Administrator role.
{% endhint %}

## PowerShell Scripts

PowerShell for PIM: [PowerShell for Azure AD roles in PIM - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/powershell-for-azure-ad-roles)

## Videos

{% embed url="https://www.youtube.com/watch?v=JyA2bMeWw5o" %}
