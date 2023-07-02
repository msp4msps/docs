# Enhanced Filtering Shall be configured if a 3rd party email filtering tool is being used

## Description

Enhanced email filtering can be set up if you have a connector in 365 (3rd party email filtering service or hybrid configuration) and your MX record does not point to Microsoft 365 or Office 365. This new feature allows you to filter email based on the actual source of messages that arrive over the connector. This is also known as skip listing and this feature will allow you to overlook, or skip, any IP addresses that are considered internal to you in order to get the last known external IP address, which should be the actual source IP address.

If you are using Defender for Office 365, this will enhance its machine learning capabilities and security around safe links/safe attachments/anti-spoofing from Microsoft’s known malicious list based off IP. In a way, you are getting a secondary layer of protection by allowing Microsoft to view the IPs of the original email and check against their database.

## Policy

Enhanced Filtering Shall be configured if a 3rd party email filtering tool is being used

## Licensing Considerations

Exchange Online Protection

## Set Up Instructions

[Enhanced filtering for connectors in Exchange Online | Microsoft Learn](https://learn.microsoft.com/en-us/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors#use-the-microsoft-365-defender-portal-to-configure-enhanced-filtering-for-connectors-on-an-inbound-connector)

Follow [these steps](https://learn.microsoft.com/en-us/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors#use-the-microsoft-365-defender-portal-to-configure-enhanced-filtering-for-connectors-on-an-inbound-connector) to configure Enhanced Filtering for Connectors on an inbound connector.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

There is no end-user impact for this setting. Depending on the providers, there may be some false positives that restrict legitimate mail to end-users.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Enhanced filtering for connectors in Exchange Online | Microsoft Learn](https://learn.microsoft.com/en-us/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors#use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-enhanced-filtering-for-connectors-on-an-inbound-connector)

## Videos

None Currently
