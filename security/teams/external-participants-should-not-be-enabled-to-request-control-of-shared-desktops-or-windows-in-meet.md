# External Participants SHOULD NOT Be Enabled to Request Control of Shared Desktops or Windows in Meet

## Description

This setting controls whether external meeting participants can request control of the shared desktop or window during the meeting. In this instance, the term “external participants” includes external users, B2B guest users, unmanaged users, and anonymous users.

While there is some inherent risk in granting an external participant control of a shared screen, legitimate use cases for this exist. Furthermore, the risk is minimal as users cannot gain control of another user’s screen unless the user giving control explicitly accepts a control request. As such, while enabling external participants to request control is discouraged, it may be done, depending on organizational need.

## Policy

* External participants SHOULD NOT be enabled to request control of shared desktops or windows in the Global (Org-wide default) meeting policy or in custom meeting policies if any exist.

## Licensing Considerations

Any Teams licensing supports this configuration.

## Set Up Instructions

Follow [these steps](https://learn.microsoft.com/en-us/microsoftteams/configure-desktop-sharing) to configure desktop sharing settings in the Teams admin center.

To ensure external participants do not have the ability to request control of the shared desktop or window in the meeting

1. Sign in to the **Microsoft Teams admin center.**
2. Select **Meetings** -> **Meeting policies.**
3. Select the **Global (Org-wide default) policy.**
4. Under the Content sharing section, set **Allow an external participant to give or request control** to **Off.**
5. If custom policies have been created, repeat these steps for each policy, selecting the appropriate policy in step 3

## End-User Impact&#x20;

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

The number of occurrences where an external participant should need to control the screen is limited. If this is something that is required for a long-term engagement, you could set up a policy to temporarily enable it for certain users within the organization.

{% hint style="info" %}
Tips

* None Currently
{% endhint %}

## PowerShell Scripts

Configure Meeting Policy [Set-CsTeamsMeetingPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)

## Videos

{% embed url="https://www.youtube.com/watch?v=EpLZUPG76RU" %}
