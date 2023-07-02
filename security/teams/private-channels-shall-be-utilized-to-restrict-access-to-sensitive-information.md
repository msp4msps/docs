---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Private Channels shall be utilized to restrict access to sensitive information

## Description

Access controls are a fundamental part of any compliance regulation. Giving access to certain Teams channels where users are collaborating on sensitive topics or sharing critical documents should follow a model of least privilege. Microsoft Teams allows you to create private channels where users can request access to the owners and all other users are prohibited from seeing the content

## &#x20;Policy

* When creating new Teams channels, a proper evaluation should be done to determine if a private channel should be selected.

## Licensing Considerations

Creating Private channels does not require any premium licensing. Any base plan with Teams included will have access to create a Teams Private Channel.

## Set Up Instructions&#x20;

Follow [these steps](https://support.microsoft.com/en-us/office/create-a-standard-or-private-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) to create a private channel in Teams

Overview of Private Channels: [Private channels in Microsoft Teams - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/private-channels)



## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

Content within a private channel is restricted to the owners and members of that channel. Users will not be able to share any documents part of the channel with any members of the org not part of the channel.

{% hint style="info" %}
Tips:

Best practices for organizing teams in Microsoft Teams: [Best practices for organizing teams - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/best-practices-organizing)
{% endhint %}

## PowerShell Scripts

* [Create Private channel in Microsoft Teams using PowerShell (morgantechspace.com)](https://morgantechspace.com/2022/06/create-private-channel-in-microsoft-teams-using-powershell.html)
* [New-TeamChannel (MicrosoftTeamsPowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/teams/new-teamchannel?view=teams-ps)

## Videos

{% embed url="https://www.youtube.com/watch?time_continue=216&v=WkAVgNKn0hs&embeds_euri=https%3A%2F%2Flearn.microsoft.com%2F&feature=emb_logo" %}

{% embed url="https://www.youtube.com/watch?v=U5EuHY2KDdY" %}
