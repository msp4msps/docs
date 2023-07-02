# Highly privileged accounts shall be cloud-only

## Description

Assign users that need to perform highly privileged tasks to cloud-only Azure AD accounts to minimize the collateral damage of an on-premises identity compromise.

## Policy

* Users that need to be assigned to highly privileged Azure AD roles SHALL be provisioned cloud-only accounts that are separate from the on-premises directory or other federated identity providers.

## Licensing Considerations

• All Microsoft Licensing Models support this configuration.

## Set Up Instructions

1. Follow [these steps](https://learn.microsoft.com/en-us/azure/active-directory/roles/view-assignments) to review the administrative roles like Global Administrator
2. Ensure that these accounts are cloud only

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">None</mark>
{% endhint %}

There is no real end user impact here as you are establishing cloud only administrative accounts.

{% hint style="info" %}
Tips

Periodically review the privileged roles within the organization to ensure compliance with this policy.
{% endhint %}

## PowerShell Scripts

Getting Sync Status: [Listing Azure AD/Office 365 User Accounts with Directory Sync Status (practical365.com)](https://practical365.com/listing-azure-ad-office-365-user-accounts-directory-sync-status/)

[View Microsoft 365 user accounts with PowerShell - Microsoft 365 Enterprise | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/enterprise/view-user-accounts-with-microsoft-365-powershell?view=o365-worldwide#view-account-synchronization-status)

## Videos

• None Currently
