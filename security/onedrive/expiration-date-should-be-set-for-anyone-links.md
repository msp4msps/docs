# Expiration Date SHOULD Be Set for Anyone Links

## Description

Files that are stored in SharePoint sites, Groups, and Teams for months and years could lead to unexpected modifications to files if shared with unauthenticated people. Configuring expiration times for Anyone links can help avoid unwanted changes. If Anyone links are enabled, the expiration date SHOULD be set to thirty days or as determined by mission needs or agency policy.

## Policy

* An expiration date SHOULD be set for Anyone links.
* Expiration date SHOULD be set to thirty days.

## Licensing Considerations

Any tenant with OneDrive for Business licensing can access this setting.

## Set-Up Instructions

[Best practices for unauthenticated sharing | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/best-practices-anonymous-sharing?view=o365-worldwide)

To set an expiration date for Anyone links across the agency (Note: Anyone links must be enabled).

1. Open the SharePoint admin center.
2. In the left-hand navigation pane, expand Policies, and then select Sharing.
3. Under Choose expiration and permissions options for Anyone links, select the These links must expire within this many days check box.
4. Enter the number of days in the box, and then click Save.

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



