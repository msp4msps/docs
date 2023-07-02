# Enable Email Encryption

## Description

Email encryption rules can be added to encrypt a message with defined rules such as having a particular keyword in the subject line or body. Most common is to add “Secure” as the key word in the subject to encrypt the message. M365/O365 Message Encryption works with Outlook.com, Yahoo!, Gmail, and other email services. Email message encryption helps ensure that only intended recipients can view message content.

## Policy

* An email encryption policy Shall be configured

## Licensing Considerations

To enable this feature, an Azure Information Protection Plan 1 subscription is required which can either be purchased standalone or as part of the following bundles:

* Microsoft 365 Business Premium
* Microsoft 365 E3
* Microsoft 365 E5

[Azure Information Protection service description - Service Descriptions | Microsoft Learn](https://learn.microsoft.com/en-us/office365/servicedescriptions/azure-information-protection)

## Set Up Instructions

[Set up Microsoft Purview Message Encryption - Microsoft Purview (compliance) | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)

[Add your brand to encrypted messages - Microsoft Purview (compliance) | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/compliance/add-your-organization-brand-to-encrypted-messages?view=o365-worldwide)

Follow [these steps](https://learn.microsoft.com/en-us/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email?view=o365-worldwide#create-mail-flow-rules-to-encrypt-email-messages-with-microsoft-purview-message-encryption) to configure a transport rule for email encryption.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

End-Users will likely need some instructions on how to use email encryption within the organization. Depending on how you role it out, they may have to type a specific subject line or leverage a built in plug-in that allows them to encrypt the message on demand. Users will need to open encrypted messages in Outlook on the web vs the email client on the desktop.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

Set up an email encryption rule: [https://github.com/msp4msps/Security/blob/master/Email%20Encryption%20Rule.ps1](https://github.com/msp4msps/Security/blob/master/Email%20Encryption%20Rule.ps1)

Set up an email encryption rule (Multi-Tenant): [https://github.com/msp4msps/Security/blob/master/Email%20Encryption%20Rule-All%20Customers.ps1](https://github.com/msp4msps/Security/blob/master/Email%20Encryption%20Rule-All%20Customers.ps1)

Verify Message Encryption: [https://learn.microsoft.com/en-us/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide#verify-microsoft-purview-message-encryption-configuration-in-exchange-online-powershell](https://learn.microsoft.com/en-us/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide#verify-microsoft-purview-message-encryption-configuration-in-exchange-online-powershell)

## Videos

{% embed url="https://www.youtube.com/watch?v=TstInDgLOdI" %}

{% embed url="https://www.youtube.com/watch?v=4eTqWvWvvpg" %}
