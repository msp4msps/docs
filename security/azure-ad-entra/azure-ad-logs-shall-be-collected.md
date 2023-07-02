# Azure AD Logs shall be collected

## Description

Azure AD logs should be a collected and periodically reviewed to detect any anomalies. Log information should be centralized in a SIEM tool, like Microsoft Sentinel, so that it can be audited and queried. Audit logs should be retained in a storage account for a minimum of 90 days.

Log events that can be collected are as follows: AuditLogs, SignInLogs, RiskyUsers, UserRiskEvents, NonInteractiveUserSignInLogs, ServicePrincipalSignInLogs, ADFSSignInLogs, RiskyServicePrincipals, and ServicePrincipalRiskEvents.

## Policy

* Azure AD Log data is sent to a SIEM and/or external storage
* Log data is periodically reviewed.
* Log data is sent to an internal or external SOC for monitoring

## Licensing Considerations

To retain Azure AD log data more than 7 days, an Azure AD P1 License is required. This license retains data for 30 days and is available to purchase standalone or as part of the following bundles:

* Microsoft 365 Business Premium
* EMS+ E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

Analyzing Sign-Ins [Analyze sign-ins with the Azure AD sign-ins log - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/reports-monitoring/quickstart-analyze-sign-in)

Route logs to a storage account: [Tutorial - Archive directory logs to a storage account - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)

Everything you want to know about Security and Audit logging in Office 365 [Everything you wanted to know about Security and Audit Logging in Office 365 | The Cloud Technologist](https://thecloudtechnologist.com/2021/10/15/everything-you-wanted-to-know-about-security-and-audit-logging-in-office-365/)

Sign In logs in Azure AD: [Sign-in logs (preview) in Azure Active Directory - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/reports-monitoring/concept-all-sign-ins)

Connect AD data to Microsoft Sentinel: [Connect Azure Active Directory data to Microsoft Sentinel | Microsoft Learn](https://learn.microsoft.com/en-us/azure/sentinel/connect-azure-active-directory)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">None</mark>
{% endhint %}

There is no end user impact to review and collect Azure AD logs.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Documenting with PowerShell: Downloading and storing the Office 365 Audit logs (With search!) (cyberdrain.com)](https://www.cyberdrain.com/documenting-with-powershell-downloading-and-storing-the-office-365-audit-logs-with-search/)

[Automating with PowerShell: Storing Office 365 audit logs longer than 90 days (cyberdrain.com)](https://www.cyberdrain.com/automating-with-powershell-storing-office-365-audit-logs-longer-than-90-days/)

[Monitoring with PowerShell: Monitoring failed logins for Office365 (cyberdrain.com)](https://www.cyberdrain.com/monitoring-with-powershell-monitoring-failed-logins-for-office365/)

[Azure AD PowerShell cmdlets for reporting - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/reports-monitoring/reference-powershell-reporting)

## Videos

{% embed url="https://www.youtube.com/watch?v=EhpofSxOdV8" %}
