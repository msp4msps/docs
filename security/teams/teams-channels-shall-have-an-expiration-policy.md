# Teams Channels shall have an expiration policy

## Description

Organizations with a large number of Teams often have Teams channels that are never actually used. This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization. Over time, such teams can accumulate and create a burden on tenant resources. To curb the number of unused teams, as an admin, you can use group expiration policy to automatically clean up unused teams. Because teams are backed by groups, group expiration policies automatically apply to teams as well.

## Policy

* &#x20;Teams channels shall have an expiration policy for inactivity

## Licensing Considerations

There are no licensing considerations for modifying the group expiration policy.

## Set Up Instructions

Resources:

[Microsoft 365 group expiration policy | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/microsoft-365-groups-expiration-policy?view=o365-worldwide#how-to-set-the-expiration-policy)

To define group expiration policies, follow the steps listed [here](https://learn.microsoft.com/en-us/microsoft-365/solutions/microsoft-365-groups-expiration-policy?view=o365-worldwide#how-to-set-the-expiration-policy)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date. When the team owner receives the notification, they can click Renew now in team settings to renew the team. To prevent accidental deletion, auto-renewal is automatically enabled for a Team in the group expiration policy. When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[New-AzureADMSGroupLifecyclePolicy (AzureAD) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/azuread/new-azureadmsgrouplifecyclepolicy?view=azureadps-2.0)

[Set-AzureADMSGroup (AzureAD) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/azuread/set-azureadmsgroup?view=azureadps-2.0)

## Videos

{% embed url="https://www.youtube.com/watch?v=zTJ1salRo1c" %}
