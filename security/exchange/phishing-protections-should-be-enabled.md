# Phishing Protections SHOULD Be Enabled

## Description

There are multiple ways to protect against phishing, including impersonation protection, mailbox intelligence and safety tips. Impersonation protection checks incoming emails to see if the sender address is similar to the users or domains on an agency-defined list. If the sender address is significantly similar, as to indicate an impersonation attempt, the email is quarantined. Mailbox intelligence is an artificial intelligence (AI)-based tool for identifying potential impersonation attempts

## Policy

* User impersonation protection SHOULD be enabled for key agency leaders.
* Domain impersonation protection SHOULD be enabled for domains owned by the agency.
* Domain impersonation protection SHOULD be added for frequent partners.
* Trusted senders and domains MAY be added in the event of false positives.
* Intelligence for impersonation protection SHALL be enabled.
* Message action SHALL be set to quarantine if the message is detected as impersonated.
* Mail classified as spoofed SHALL be quarantined.
*   All safety tips SHALL be enabled, including:

    ‒ first contact.

    ‒ user impersonation.

    ‒ domain impersonation.

    ‒ user impersonation unusual characters.

    ‒ “?” for unauthenticated senders for spoof.

    ‒ “via” tag.
* The above configurations SHALL be set in the default policy and SHOULD be set in all existing custom policies.

## Licensing Considerations

This setting requires Defender for Office 365 Plan 1 or Plan 2 which can be purchased standalone or as part of the following bundles:

* Microsoft 365 Business Premium
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

[Configure anti-phishing policies in EOP - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-phishing-policies-eop-configure?view=o365-worldwide)

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Select Threat policies.
4. Under Policies, select Anti-phishing.
5. Select the Office365 AntiPhish Default (Default) policy.
6. Click Edit protection settings.
7. Check Enable users to protect.
8. Click Manage sender(s), then add users that merit impersonation protection.
9. Check Enable domains to protect.
10. Check Include domains I own.
11. Check Include custom domains.
12. Click Manage custom domains(s) to add the domains of frequent partners.
13. Check Enable mailbox intelligence (Recommended).
14. Check Enable Intelligence for impersonation protection (Recommended).

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

With this setting in place, users will better protection against spoofing attempts against their email. With additional protections, there is a higher chance of false positives that could negatively impact the user in which they do not receive legitimate mail.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[https://learn.microsoft.com/en-us/powershell/module/exchange/set-antiphishpolicy?view=exchange-ps](https://learn.microsoft.com/en-us/powershell/module/exchange/set-antiphishpolicy?view=exchange-ps)

## Videos

{% embed url="https://www.youtube.com/watch?v=UYRkY0eRmGc" %}
