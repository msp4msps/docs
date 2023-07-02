# Expiration Times for Guest Access to a Site SHOULD Be Determined by specific needs

## Description

SharePoint allows sharing with users who are outside the agency, which is convenient but may pose a data loss or other information security risk. This working group recommends setting an expiration time for guest access to the site or OneDrive

## Policy

* Expiration timers for ‘guest access to a site or OneDrive’ and ‘people who use a verification code’ SHOULD be set.
* Expiration timers SHOULD be set to 30 days.

## Licensing Considerations

Any tenant with SharePoint online licensing can access this setting.

## Set-Up Instructions

[Managing SharePoint Online Security: A Team Effort | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/community/sharepoint-security-a-team-effort)

To limit external sharing by domain, in the SharePoint admin center:

1. Select Policies -> Sharing.
2. Expand More external sharing settings.
3. Select Guest access to a site or OneDrive will expire automatically after this many days.
4. Enter “30” days.
5. Select People who use a verification code must reauthenticate after this many days.
6. Enter “30” days.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

• Users may have to reshare new links if the existing ones expire before the interaction with external users is complete.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Set-SPOSite (Microsoft.Online.SharePoint.PowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps)

[Best practices for unauthenticated sharing | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/best-practices-anonymous-sharing?view=o365-worldwide#set-an-expiration-date-for-anyone-links)

## Videos&#x20;

None Currently&#x20;



