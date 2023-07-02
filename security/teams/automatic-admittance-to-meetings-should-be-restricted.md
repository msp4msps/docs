# Automatic Admittance to Meetings SHOULD Be Restricted

## Description

This setting controls which meeting participants wait in the lobby before they are admitted to the meeting

## Policy

* Anonymous users, including dial-in users, SHOULD NOT be admitted automatically.
* Internal users SHOULD be admitted automatically.
* B2B guest users MAY be admitted automatically.
* The above settings SHOULD be set in the Global (Org-wide default) meeting policy.
* Custom meeting policies MAY be created that allow more flexibility for specific users.

## Licensing Considerations

Any Teams licensing supports this configuration.

## Set Up Instructions

Microsoft Resources: [Manage meeting policies for participants and guests - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/meeting-policies-participants-and-guests)

To configure settings for automatic meeting admittance:

1. Sign in to the **Microsoft Teams admin center.**
2. Select **Meetings** -> **Meeting policies**.
3. Select the **Global (Org-wide default) policy.**
4. Under the **Participants & guests section**, ensure **Automatically admit people** is **not set to Everyone.**
5. In the same section, set **Dial-in users can bypass the lobby** to **Off.**
6. If custom policies have been created, repeat these steps for each policy, selecting the appropriate policy in step 3

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Internal Users will need to manually admit anonymous and/or external users to meetings when they enter the lobby.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

Configure Meeting Policy [Set-CsTeamsMeetingPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)

## Videos

None Currently
