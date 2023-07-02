# Alerts SHALL Be Enabled

## Description

Microsoft Defender includes several prebuilt alert policies, many of which pertain to Exchange Online. These alerts give admins better real-time insight into possible security incidents.

## Policy

At a minimum, the following alerts SHALL be enabled:

* Suspicious email sending patterns detected.
* Suspicious connector activity
* Suspicious email forwarding activity.
* Unusual increase in email reported as phish.
* Messages have been delayed.
* Tenant restricted from sending unprovisioned email.
* Tenant restricted from sending email.
* Malware campaign detected after delivery.
* A potentially malicious URL click was detected.

The alerts SHOULD be sent to a monitored address or incorporated into a security incident and event management (SIEM) tool.

## Licensing Considerations

This setting requires Defender for Office 365 Plan 1 or Plan 2 which can be purchased standalone or as part of the following bundles:

* Defender for Office 365 Plan 1/2
* Microsoft 365 Business Premium
* Office 365 E5/A5/G5
* Microsoft 365 E5/A5/G5
* Microsoft 365 E5/A5/G5 Information Protection and Governance
* Microsoft 365 E5/A5/G5/F5 Compliance and F5 Security & Compliance

## Set Up Instructions

[Microsoft 365 alert policies - Microsoft Purview (compliance) | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/compliance/alert-policies?view=o365-worldwide)

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Select Alert Policy.
4. Click the policy name.
5. Ensure Status is set to On.
6. Ensure Email recipients includes at least one monitored address

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

[New-ProtectionAlert (ExchangePowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/exchange/new-protectionalert?view=exchange-ps)

## Videos

{% embed url="https://www.youtube.com/watch?v=fuxPRQGGX7k" %}

