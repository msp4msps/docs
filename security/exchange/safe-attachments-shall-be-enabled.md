# Safe Attachments SHALL Be Enabled

## Description

The Safe Attachments will scan messages for attachments with malicious content. It routes all messages and attachments that do not have a virus/malware signature to a special environment. The process then uses machine learning and analysis techniques to detect malicious intent. Enabling this feature may slow down message delivery to the user due to the scanning.

## Policy

* At least one Safe Attachments Policy SHALL include all agency domains—and by extension—all users.
* The action for malware in email attachments SHALL be set to block.
* Redirect emails with detected attachments to an agency-specified email SHOULD be enabled.

## Licensing Considerations

This setting requires Defender for Office 365 Plan 1 or Plan 2 which can be purchased standalone or as part of the following bundles:

* Defender for Office 365 Plan 1/2
* Microsoft 365 Business Premium
* Office 365 E5/A5/G5
* Microsoft 365 E5/A5/G5
* Microsoft 365 E5/A5/G5 Information Protection and Governance
* Microsoft 365 E5/A5/G5/F5 Compliance and F5 Security & Compliance

## Set Up Instructions

[Safe Attachments - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-attachments-about?view=o365-worldwide#safe-attachments-policy-settings)

[Set up Safe Attachments policies in Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-attachments-policies-configure?view=o365-worldwide#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)

To configure safe attachments for Exchange Online, follow the instructions listed on [Use the Microsoft 365 Defender portal to create Safe Attachments policies.](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Select Threat policies.
4. Under Policies, select Safe Attachments.
5. Click Create to start a new policy.
6. Give the new policy an appropriate name and description.
7. Under domains, enter all organization tenant domains. All users under these domains will be added to the policy.
8.  Under Safe Attachments unknown malware response, select Block.

    Set the Quarantine policy to AdminOnlyAccessPolicy.
9. Click Next, then Submit.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

With this setting in place, there may be some latency in email flow while the attachment is being scanned before delivery. If the attachment is found to be malicious, the email will be blocked from sending.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Set up Safe Attachments policies in Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-attachments-policies-configure?view=o365-worldwide#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)

[Security/ATP Implementation.ps1 at master · msp4msps/Security (github.com)](https://github.com/msp4msps/Security/blob/master/ATP%20Implementation.ps1)

## Videos

{% embed url="https://www.youtube.com/watch?v=ZaJhALRsi9U" %}

{% embed url="https://www.youtube.com/watch?v=njFTlDSMnJU" %}

{% embed url="https://www.youtube.com/watch?v=d1MGU4vw9D8" %}
