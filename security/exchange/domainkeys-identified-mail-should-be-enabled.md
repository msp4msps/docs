# DomainKeys Identified Mail SHOULD Be Enabled

## Description

DomainKeys Identified Mail (DKIM) allows digital signatures to be added to email messages in the message header, providing a layer of both authenticity and integrity to emails. As with SPF, DKIM relies on DNS records; thus, its deployment depends on how an organization manages its DNS. DKIM is enabled for the tenant’s default domain (e.g., on microsoft.com domains), but it must be manually enabled for custom domains.

## Policy

* DKIM SHOULD be enabled for any custom domain.

## Licensing Considerations

DKIM signing is included with Exchange Online Protection (EOP), which is included in all Microsoft 365 subscriptions that contain Exchange Online mailboxes.

## Set Up Instructions

[How to use DKIM for email in your custom domain - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-dkim-configure?view=o365-worldwide)

[How Sender Policy Framework (SPF) prevents spoofing - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-anti-spoofing?view=o365-worldwide)

[Support for validation of Domain Keys Identified Mail (DKIM) signed messages - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-dkim-support-about?view=o365-worldwide)

To enable DKIM, follow the instructions listed on [Steps to Create, enable and disable DKIM](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-dkim-configure?view=o365-worldwide#steps-to-create-enable-and-disable-dkim-from-microsoft-365-defender-portal) from Microsoft 365 Defender portal | Microsoft Docs.

1. Navigate to the Microsoft 365 Defender admin center.
2. Go to Policies & Rules.
3. Go to Threat Policies.
4. Select DKIM.
5. Select your domain.
6. Switch Sign messages for this domain with DKIM signatures to Enabled.

If you are enabling DKIM for the first time, a pop-up window listing Canonical Name (CNAME) records displays. Publish these records to your DNS service provider.

Return to the DKIM page on the Defender admin center to finish enabling DKIM.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>&#x20;
{% endhint %}

While there is no direct impact to end-users, they should experience better outbound mail flow delivery with DKIM in place.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

{% embed url="https://www.youtube.com/watch?v=r-Qz52BUL6E" %}
