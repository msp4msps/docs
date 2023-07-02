# Anonymous Users SHALL NOT Be Enabled to Start Meetings

## Description

This setting controls which meeting participants can start a meeting. In this instance, the term “anonymous users” refers to any Teams users joining calls that are not authenticated through the company’s tenant.

## Policy

* Anonymous users SHALL NOT be enabled to start meetings in the Global (Org-wide default) meeting policy or in custom meeting policies if any exist.

## Licensing Considerations

Any Teams licensing supports this configuration.

## Set Up Instructions

Microsoft Resources: [Control who can bypass the meeting lobby in Microsoft Teams - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/who-can-bypass-meeting-lobby)

To configure settings for anonymous users:

1. Sign in to the **Microsoft Teams admin center**.
2. Select Meetings -> **Meeting policies.**
3. Select the **Global (Org-wide default) policy**.
4. Under the **Participants & guests** section, set L**et anonymous people start a meeting** to **Off.**
5. If custom policies have been created, repeat these steps for each policy, selecting the appropriate policy in step 3

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>&#x20;
{% endhint %}

This is only affecting external users who enter a meeting as anonymous.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

Configure Meeting Policy [Set-CsTeamsMeetingPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)

## Videos

None Currently
