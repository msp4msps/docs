# Only Approved Apps SHOULD Be Installed

## Description

Teams can integrate with the following classes of apps:

* Microsoft apps: apps published by Microsoft.
* Third-party apps: apps not authored by Microsoft, published to the Teams store.
* Custom apps: apps not published to the Teams store, such as apps under development, that users “sideload” into Teams

Only authorized and approved applications should be available to end-users to manage exfiltration of corporate data. Additionally, unmanaged applications may have certain vulnerabilities that exploit users, devices, or data.

## Policy

* Organizations SHOULD allow all apps published by Microsoft, but MAY block specific Microsoft apps as needed.
* Organizations SHOULD NOT allow installation of all third-party apps or custom apps, but MAY allow specific apps as needed.
* Organizations shall establish policy dictating the app review and approval process to be used by the company.

## Licensing Considerations

Any Teams licensing supports this configuration.

## Set Up Instructions

Resources:

[Manage app permission policies in Microsoft Teams - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/teams-app-permission-policies)

To restrict which Team apps can be installed:

1. Sign in to the Microsoft Teams admin center.
2. Select Teams apps -> Permission policies.
3. Select Global (Org-wide default).
4. Under Microsoft apps, select Allow all apps, unless specific apps need to be disallowed, in which case select Block specific apps and allow all others.
5. Set Third-party apps to Block all apps, unless specific apps have been approved by the agency, in which case select Allow specific apps and block all others.
6. Set Custom apps to Block all apps, unless specific apps have been approved by the agency, in which case select Allow specific apps and block all others.
7. Click Save.
8. If custom policies have been created, repeat these steps for each policy, selecting the appropriate policy in step 3.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

This will vary depending on the organization but users will not be able to add applications from the Apps section of team unless preapproved in the Teams admin center. A formal process for requesting new Teams apps should be properly documented and communicated.

{% hint style="info" %}
Tips

• Make sure users understand how to request a new applications for Microsoft Teams.
{% endhint %}

## PowerShell Scripts

[How to manage Microsoft Teams app permission policy – PARAS DODHIA BLOG](https://blog.dodhia.co/how-to-manage-microsoft-teams-app-permission-policy/)

[New-CsTeamsAppPermissionPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/new-csteamsapppermissionpolicy?view=skype-ps)

[Set-CsTeamsAppPermissionPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csteamsapppermissionpolicy?view=skype-ps)

## Videos

None Currently
