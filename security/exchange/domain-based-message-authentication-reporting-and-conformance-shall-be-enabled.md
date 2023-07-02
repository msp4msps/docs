# Domain-Based Message Authentication, Reporting, and Conformance SHALL Be Enabled

## Description

Domain-based Message Authentication, Reporting, and Conformance (DMARC) works with SPF and DKIM to authenticate mail senders and ensure that destination email systems can validate messages sent from your domain. DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks

## Policy

* A DMARC policy SHALL be published for every custom domain.
* The DMARC message rejection option SHALL be “p=reject.”

## Licensing Considerations

Any tenant can perform this configuration

## Set Up Instructions

[Use DMARC to validate email, setup steps - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-dmarc-configure?view=o365-worldwide#best-practices-for-implementing-dmarc-in-microsoft-365)

[Use DMARC to validate email, setup steps - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/email-authentication-dmarc-configure?view=o365-worldwide#how-microsoft-365-handles-inbound-email-that-fails-dmarc)

DMARC implementation varies depending on how an agency manages its DNS records. See [Form the DMARC TXT record for your domain | Microsoft Docs](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/use-dmarc-to-validate-email?view=o365-worldwide#step-4-form-the-dmarc-txt-record-for-your-domain) for Microsoft guidance. DMARC records can be requested using the PowerShell tool Resolve-DnsName. For example:

Resolve-DnsName \_dmarc.example.com txt

Replace “example.com” in the example with the domain(s) used for your agency’s emails. Ensure that (1) the DNS record exists, (2) “p=reject;” is included in the policy returned from the query

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

While there is no direct impact to end-users, they should experience better outbound mail flow delivery with DMARC in place,

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

{% embed url="https://www.youtube.com/watch?v=r-Qz52BUL6E" %}
