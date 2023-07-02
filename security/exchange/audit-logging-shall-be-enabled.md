# Audit Logging SHALL Be Enabled

## Description

To view data in threat protection reports, email security reports, and Explorer, audit logging must be turned on. By default, Microsoft retains the audit logs for only 90 days.

## Policy

Audit logging SHALL be enabled.

## Licensing Considerations

By default, Microsoft retains the audit logs for only 90 days for every Microsoft Tenant

Advanced audit capabilities, including the creation of a custom audit log retention policy, requires E5/G5 licenses or E3/G3 licenses with add-on compliance licenses. Additionally, maintaining logs in the Microsoft 365 environment for longer than one year requires an add-on license. For more information, see [Licensing requirements | Microsoft Docs.](https://learn.microsoft.com/en-us/microsoft-365/compliance/audit-solutions-overview?view=o365-worldwide#licensing-requirements)

## Set Up Instructions

Auditing can be enabled from the Microsoft 365 compliance admin center and the Exchange Online PowerShell. Follow the instructions listed on [Turn on auditing.](https://docs.microsoft.com/en-us/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide#turn-on-auditing)

1. Sign in to the Microsoft 365 compliance admin center.
2. Under Solutions, select Audit.
3. If auditing is not enabled, a banner displays and prompts that the user and admin activity start being recorded.
4. Click the Start recording user and admin activity banner.

To set up advanced audit, see [Set up Advanced Audit in Microsoft 365 | Microsoft](https://docs.microsoft.com/en-us/microsoft-365/compliance/set-up-advanced-audit?view=o365-worldwide) Docs.

To create an audit retention policy, follow the instructions listed on [Create an audit log retention policy.](https://docs.microsoft.com/en-us/microsoft-365/compliance/audit-log-retention-policies?view=o365-worldwide#create-an-audit-log-retention-policy)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">None</mark>
{% endhint %}

There is no end-user impact for this setting

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

To check the current logging status via PowerShell:

1. Connect to Exchange Online
2. Run the following command

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled. 
```

To enable logging via PowerShell

```powershell
Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true.
```

## Videos

{% embed url="https://www.youtube.com/watch?v=N1_AlXoUBR4" %}

{% embed url="https://www.youtube.com/watch?v=-UNIV6La0a8" %}
