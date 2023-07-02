# Sender Policy Framework SHALL Be Enabled

## Description

The Sender Policy Framework (SPF) is a mechanism that allows domain administrators to specify which Internet Protocol (IP) addresses are explicitly approved to send email on behalf of the domain, facilitating detection of spoofed emails. SPF is not configured through the Exchange admin center, but rather via the Domain Name Service (DNS) records hosted by the organization’s domain.

## Policy

* A list of approved IP addresses for sending mail SHALL be maintained
* An SPF policy(s) that designates only these addresses as approved senders SHALL be published.

## Licensing Considerations

Any tenant can configure this setting.

## Set Up Instructions

[Set up SPF to help prevent spoofing - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-spf-configure?view=o365-worldwide)

[How Sender Policy Framework (SPF) prevents spoofing - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-anti-spoofing?view=o365-worldwide)

Adding SPF records to a domain will vary depending on where the domain is hosted. Follow [these steps](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-spf-configure?view=o365-worldwide#create-or-update-your-spf-txt-record) for configuring an SPF record for Exchange Online.

## End-User Impact&#x20;

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Without proper SPF configuration, is possible that users will have their email rejected or marked as spam when sending outbound messages.

{% hint style="info" %}
Tips

* Optimize SPF Record: [How To Optimize SPF Record? v spf1 a mx (easydmarc.com)](https://easydmarc.com/blog/how-to-optimize-spf-record/)
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

{% embed url="https://www.youtube.com/watch?v=r-Qz52BUL6E" %}
