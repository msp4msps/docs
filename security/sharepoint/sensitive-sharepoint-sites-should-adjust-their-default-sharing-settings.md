# Sensitive SharePoint Sites SHOULD Adjust Their Default Sharing Settings

## Description

SharePoint allows sharing with users who are outside the agency, which is convenient but may pose a data loss or other information security risk. This working group recommends outside of the default organizational settings agencies should evaluate each created site and adjust sharing settings best aligned to their respective sensitivity level.

## Policy

Sharing settings for specific SharePoint sites SHOULD align to their sensitivity level

## Licensing Considerations

Any tenant with SharePoint online licensing can access this setting.

## Set-Up Instructions

[Managing SharePoint Online Security: A Team Effort | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/community/sharepoint-security-a-team-effort)

To limit external sharing by domain, in the SharePoint admin center:

1. Select Sites.
2. Select Active sites.
3. Select Site name.
4. Select Add domains.
5. Select Policies.
6. Under external sharing, select Edit.
7. Select permissions aligning to the risk posture associated with the sensitivity of the SharePoint site.
8. Select Save.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

Depending on the selection here, users will be restricted in sharing links of documents within the SharePoint Site.

{% hint style="info" %}
Tips

There should be guidance provided on document repository structure.

Leverage some type of form for when users want to create a new SharePoint site to see if it will contain sensitive information.
{% endhint %}

## PowerShell Scripts

[Set-SPOSite (Microsoft.Online.SharePoint.PowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps)

## Videos&#x20;

{% embed url="https://www.youtube.com/watch?v=mFVhzJKyfGg" %}



