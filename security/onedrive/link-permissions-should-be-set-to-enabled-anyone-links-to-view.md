# Link Permissions SHOULD Be Set to Enabled Anyone Links to View

## Description

The Anyone links default to allow people to edit files, as well as edit and view files and upload new files to folders. To allow unauthenticated sharing but keep unauthenticated people from modifying the agency's content, consider setting the file and folder permissions to View.

## Policy

* Anyone link permissions SHOULD be limited to View.

## Licensing Considerations

Any tenant with OneDrive for Business licensing can access this setting.

## Set-Up Instructions

[Best practices for unauthenticated sharing | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/best-practices-anonymous-sharing?view=o365-worldwide)

To set an expiration date for Anyone links across the agency (Note: Anyone links must be enabled).

1. Open the SharePoint admin center.'
2. In the left-hand navigation pane, expand Policies, then select Sharing.
3. Under Advanced settings for Anyone links, set the file and folder permissions to View.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Users may have to reshare new links if the existing ones expire before the interaction with external users is complete.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Set-SPOSite (Microsoft.Online.SharePoint.PowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps)

## Videos&#x20;

None Currently



