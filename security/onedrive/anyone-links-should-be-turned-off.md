# Anyone Links SHOULD Be Turned Off

## Description

Unauthenticated sharing (Anyone links) is used to share data without authentication and users are free to pass it on to others outside the agency. To prevent users from unauthenticated sharing of content, turn off Anyone sharing for users outside the tenant when accessing content in SharePoint, Groups, or Teams.

## Policy

* Anyone links SHOULD be disabled.

## Licensing Considerations

Any tenant with OneDrive for Business licensing can access this setting.

## Set-Up Instructions

[Limit accidental exposure | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/share-limit-accidental-exposure?view=o365-worldwide)

Note: OneDrive settings can be more restrictive than the SharePoint setting, but not more permissive.

To turn off Anyone links for the agency:

1. Open the SharePoint admin center.
2. In the left-hand navigation pane, expand Policies, then select Sharing.
3. Set the SharePoint external sharing settings to New and existing guests, then set OneDrive to New and existing guests.
4. Click Save.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

With this setting enabled, users will have to specify users that can access the link. If the link is forwarded to other users internally or externally, those users will not be able to access the link.

{% hint style="info" %}
Tips

• A formal process should be put into place for requesting guest users and sharing company data.
{% endhint %}

## PowerShell Scripts

[Set-SPOSite (Microsoft.Online.SharePoint.PowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps)

## Videos&#x20;

None Currently



