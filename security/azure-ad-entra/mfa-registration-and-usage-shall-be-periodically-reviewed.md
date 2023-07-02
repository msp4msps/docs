# MFA registration and usage shall be periodically reviewed

## Description

MFA registration should periodically be reviewed to ensure that there are no gaps or misconfigurations of deployment. MFA can be monitored natively within Azure Active Directory or with 3rd party tools.

## Policy

* MFA registration details and usage shall be monitored on a defined schedule.

## Licensing Considerations

Viewing Authentication Activity in Azure AD requires an Azure AD P1 license which can be purchased standalone or through the following common plans:

* Microsoft 365 Business Premium
* EMS + E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

MFA reports can also be derived from PowerShell which does not require an Azure AD P1 license and can be used with any Microsoft licensing model

## Set Up Instructions

To view the Authentication Activity: [Authentication Methods Activity - Azure Active Directory - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/authentication/howto-authentication-methods-activity)

Using the Azure AD sign-ins report: [Sign-in event details for Azure AD Multi-Factor Authentication - Azure Active Directory - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/authentication/howto-mfa-reporting)

Usage Graph API: [List credentialUserRegistrationDetails - Microsoft Graph beta | Microsoft Learn](https://learn.microsoft.com/en-us/graph/api/reportroot-list-credentialuserregistrationdetails?view=graph-rest-beta\&tabs=http)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">None</mark>
{% endhint %}

There is no end-user impact when looking at log information or reports on MFA.

{% hint style="info" %}
Tips

Try to review this information at least quarterly

The [registration and reset events](https://learn.microsoft.com/en-us/azure/active-directory/authentication/howto-authentication-methods-activity#registration-and-reset-events) of the Authentication methods section can also be used to investigate potential post-breach activity. Attackers sometimes reset MFA registration methods after accessing a compromised account.
{% endhint %}

## PowerShell Scripts

MFA Status Reporting (Multi-tenant): [Security/MFA Status\_Custom Control\_All Customers.ps1 at master · msp4msps/Security (github.com)](https://github.com/msp4msps/Security/blob/master/MFA%20Status\_Custom%20Control\_All%20Customers.ps1)

Find Global Admins without MFA: [Security/Customer-Global Admin without MFA.ps1 at master · msp4msps/Security (github.com)](https://github.com/msp4msps/Security/blob/master/Customer-Global%20Admin%20without%20MFA.ps1)

## Videos

{% embed url="https://www.youtube.com/watch?v=k0uHPT7pBRs" %}

{% embed url="https://www.youtube.com/watch?v=SK1zgqaAZ2E" %}
