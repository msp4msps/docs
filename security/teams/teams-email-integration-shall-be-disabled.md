# Teams Email Integration SHALL Be Disabled

## Description

Teams provides an optional feature that allows channels to have an email address and receive email. These channel email addresses are not under the tenant’s domain; rather, they are associated with a Microsoft-owned domain, teams.ms. As such, although some basic checks are performed, companies do not have control over the security settings associated with this email. For this reason, email channel integration should be disabled.

## Policy

* &#x20;Teams email integration SHALL be disabled.

## Licensing Considerations

Teams email integration is only available with E3/E5 licenses. It is not available in GCC or DoD tenants.



## Set Up Instructions

Resources:

[How to Control Sending Email to Teams Channels | Practical365](https://practical365.com/how-to-control-sending-email-to-teams-channels/)

To ensure that teams email integration is disabled:

1. Sign in to the Microsoft Teams admin center.
2. Select Teams -> Teams Settings.
3. Under the Email integration section, set Allow users to send emails to a channel email address to Off.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Adoption of the Teams email integration should be low or nonexistent. Make sure to review and active Teams emails in use and notify users accordingly before disabling this feature.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

{% embed url="https://www.youtube.com/watch?v=S6CftqMsGs4" %}
