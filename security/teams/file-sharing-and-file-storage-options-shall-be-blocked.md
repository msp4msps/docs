# File Sharing and File Storage Options shall be blocked

## Description

By default, users can add external third-party storage providers like Google and Drobox to their Teams channels for file storage. Only managed, trusted providers should be allowed for data loss prevention purposes.

## Policy

* &#x20;File Sharing and File Storage Options are disabled.

## Licensing Considerations

Any Teams licensing supports this configuration.

## Set Up Instructions

Resources:

[Controlling Third Party Cloud Storage Access for Microsoft Teams | Practical365](https://practical365.com/third-party-cloud-storage/)

To restrict file sharing and file storage options:

1. Go to the Microsoft Teams Admin Center
2. Choose Teams -> Teams Settings.
3. Under Files turn off all 3rd part file storage applications
4. Click Save

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

This will very depending on the organization but in most cases, end-users should be leveraging native file storage options such as SharePoint or OneDrive. Ensure that end-users are not uploading files to 3rd parties before configuring this setting.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Get-CsTeamsClientConfiguration (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/get-csteamsclientconfiguration?view=skype-ps)

[Set-CsTeamsClientConfiguration (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)

## Videos

{% embed url="https://www.youtube.com/watch?v=iyoI0BK60Ns" %}

{% embed url="https://www.youtube.com/watch?v=HhYUa6hf6WA" %}
