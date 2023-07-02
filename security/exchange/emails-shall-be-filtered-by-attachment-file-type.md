# Emails SHALL Be Filtered by Attachment File Type

## Description

For some types of files (e.g., executable files), the dangers of allowing them to be sent over email outweigh any potential benefits. Some services, such as the Common Attachment Filter of Microsoft Defender, filter emails based on the attachment file types. Use of Microsoft Defender for this purpose is not strictly required; instead, equivalent products that fulfill the requirements outlined in this baseline setting may be used

## Policy

* &#x20;Emails SHALL be filtered by the file types of included attachments
* Disallowed file types SHALL be determined and set. At a minimum, click-to-run files SHOULD be blocked (e.g., .exe, .cmd, and .vbe).

## Licensing Considerations

This setting requires Defender for Office 365 Plan 1 or Plan 2 which can be purchased standalone or as part of the following bundles:

* Microsoft 365 Business Premium
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

[Configure anti-malware policies - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-malware-policies-configure?view=o365-worldwide)

[Anti-malware protection - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-malware-protection-about?view=o365-worldwide#anti-malware-policies)

To enable common attachments filter in the default policy:

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Select Threat policies.
4. Under Policies, select Anti-malware.
5. Select the Default (Default) policy.
6. Click Edit protection settings.
7. Check Enable the common attachments filter.
8. Click Customize file types as needed.
9. Click Save.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

With this setting in place, users will not be able to receive attachments specified in the policy.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[https://learn.microsoft.com/en-us/powershell/module/exchange/set-malwarefilterpolicy?view=exchange-ps](https://learn.microsoft.com/en-us/powershell/module/exchange/set-malwarefilterpolicy?view=exchange-ps)

## Videos

{% embed url="https://www.youtube.com/watch?v=R-0YVW6pNt4" %}
