# Link Protection SHOULD Be Enabled

## Description

Microsoft Defender protects users from malicious links included in Teams messages by prependinghttps://\*.safelinks.protection.outlook.com/?url= to URLs included in the messages.

By prepending the safe links URL, Microsoft can proxy the initial URL through their scanning service. Their proxy performs the following checks:

* Compares the URL with a block list
* Compares the URL with a list of know malicious sites
* If the URL points to a downloadable file, applies real-time file scanning

## Policy

* URL comparison with a block-list SHOULD be enabled.
* Direct download links SHOULD be scanned for malware.
* User click tracking SHOULD be enabled.

## Licensing Considerations

Safe Links can be configured with the Following plans

* Defender for Office 365 Plan 1/2
* Microsoft 365 Business Premium
* Office 365 E5/A5/G5
* Microsoft 365 E5/A5/G5
* Microsoft 365 E5/A5/G5 Information Protection and Governance
* Microsoft 365 E5/A5/G5/F5 Compliance and F5 Security & Compliance

## Set Up Instructions

Resources:

[Set up Safe Links policies in Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-policies-configure?view=o365-worldwide#step-1-use-powershell-to-create-a-safe-links-policy)

To enable Safe Links for Teams follow the steps listed [here](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-policies-configure?view=o365-worldwide#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

When safe links is enabled in Teams users will experience more latency for webpages to open while the URL is being scanned. If a link is detected as malicious the user will see a warning message. Depending on how the policy is configured, the user will/will not be able to proceed to the webpage.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Set up Safe Links policies in Microsoft Defender for Office 365 - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/safe-links-policies-configure?view=o365-worldwide#step-1-use-powershell-to-create-a-safe-links-policy)

## Videos

{% embed url="https://www.youtube.com/watch?v=An7YLf_dfpk" %}
