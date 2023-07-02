# Safe Link Policies SHOULD Be Enabled

## Description

When enabled, URLs in emails are rewritten by prepending:

https://\*.safelinks.protection.outlook.com/?url=

to the original URL. This change can only be seen by either clicking the URL or copying and pasting it; the end-user, even when hovering over the URL in their email, will still only see the original URL. By prepending the safe links URL, Microsoft can proxy the initial URL through their scanning service. Their proxy can perform the following:

* Compares the URL with a block list
* Compares the URL with a list of know malicious sites
* If the URL points to a downloadable file, applies real-time file scanning

If all checks pass, the user is redirected to the original URL

## Policy

* The Safe Links Policy SHALL include all agency domains—and by extension—all users.
* URL rewriting and malicious link click checking SHALL be enabled.
* Malicious link click checking SHALL be enabled with Microsoft Teams.
* Real-time suspicious URL and file-link scanning SHALL be enabled.
* URLs SHALL be scanned completely before message delivery.
* Internal agency email messages SHALL have safe links enabled.
* User click tracking SHALL be enabled.
* Safe Links in Office 365 apps SHALL be turned on.
* Users SHALL NOT be enabled to click through to the original URL.

## Licensing Considerations

This setting requires Defender for Office 365 Plan 1 or Plan 2 which can be purchased standalone or as part of the following bundles:

* Defender for Office 365 Plan 1/2
* Microsoft 365 Business Premium
* Office 365 E5/A5/G5
* Microsoft 365 E5/A5/G5
* Microsoft 365 E5/A5/G5 Information Protection and Governance
* Microsoft 365 E5/A5/G5/F5 Compliance and F5 Security & Compliance

## Set Up Instructions

Resources:

[Complete Safe Links overview for Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-about?view=o365-worldwide)

[Set up Safe Links policies in Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-policies-configure?view=o365-worldwide)

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Select Threat policies.
4. Under Policies, select Safe Links.
   1. Create a Safe Links Policy.
      1. Assign the new policy an appropriate name and description.
         1. Include all tenant domains. All users under those domains will be added.
            1. On the URL & click protection settings page:
               1. Select On: Safe Links checks a list of known, malicious links when users click links in email. URLs are rewritten by default.
               2. Select Apply Safe Links to email messages sent within the organization.
               3. Select Apply real-time URL scanning for suspicious links and links that point to files.
               4. Select Wait for URL scanning to complete before delivering the message.
            2. On the URL & click protection settings page, under Teams, select On: Safe Links checks a list of known, malicious links when users click links in Microsoft Teams. URLs are not rewritten.
            3. On the URL & click protection settings page, under Office 365 Apps, select On: Safe Links checks a list of known, malicious links when users click links in Microsoft Office Apps. URLs are not rewritten.
            4. On the URL & click protection settings page, under Click protection settings:
               1. Select Track User Clicks.
               2. Do not select Let users click through to the original URL.
            5. Review the new policy, then click Submit.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

With this setting in place, there may be some latency in email flow while the URL is being scanned before delivery. When users click on a link and the link is found to be malicious, users will get a page describing the malicious link and will not be able to proceed to the webpage.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Set up Safe Links policies in Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-policies-configure?view=o365-worldwide#use-powershell-to-create-safe-links-policies)

[Security/ATP Implementation.ps1 at master · msp4msps/Security (github.com)](https://github.com/msp4msps/Security/blob/master/ATP%20Implementation.ps1)

## Videos

{% embed url="https://www.youtube.com/watch?v=ZaJhALRsi9U" %}

{% embed url="https://www.youtube.com/watch?v=vhIJ1Veq36Y" %}
