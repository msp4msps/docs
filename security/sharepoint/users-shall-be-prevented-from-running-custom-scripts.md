# Users SHALL Be Prevented from Running Custom Scripts

## Description

Allowing users to run custom scripts can potentially allow malicious scripts to run in a trusted environment. For this reason, running custom scripts should not be allowed

## Policy

* Users SHALL be prevented from running custom scripts

## Licensing Considerations

Any tenant with SharePoint online licensing can access this setting.

## Set-Up Instructions

[Managing SharePoint Online Security: A Team Effort | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/community/sharepoint-security-a-team-effort)[Allow or prevent custom script - SharePoint in Microsoft 365 | Microsoft Learn](https://learn.microsoft.com/en-us/sharepoint/allow-or-prevent-custom-script)

In the SharePoint Classic admin center:

1. Scroll to the Custom Script setting and select both of the following:
   1. Prevent users from running custom script on personal sites.
   2. Prevent users from running custom script on self-service created sites.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

There shouldn’t be many users looking to run custom scripts in SharePoint

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Allow or prevent custom script - SharePoint in Microsoft 365 | Microsoft Learn](https://learn.microsoft.com/en-us/sharepoint/allow-or-prevent-custom-script#to-allow-custom-script-on-other-sharepoint-sites)

## Videos&#x20;

None Currently



