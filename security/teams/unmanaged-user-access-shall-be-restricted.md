# Unmanaged User Access SHALL Be Restricted

## Description

Blocking contact with unmanaged Teams users prevents these users from looking up internal users by their email address and initiating chats and calls within Teams. These users would still be able to join calls, assuming anonymous join is enabled. Additionally, unmanaged users may be added to Teams chats if the internal user initiates the contact. Unmanaged accounts are ones not managed by an organization, typically Teams personal accounts.

## Policy

* Unmanaged users SHALL NOT be enabled to initiate contact with internal users.
* Internal users SHOULD NOT be enabled to initiate contact with unmanaged users.

## Licensing Considerations

Any Teams licensing supports this configuration.



## Set Up Instructions

Microsoft Resources:

[Manage external meetings and chat - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/manage-external-access#manage-contact-with-external-teams-users-not-managed-by-an-organization)

To block unmanaged users for initiating contact:

1. Sign in to the Microsoft Teams admin center.
2. Select Users -> External access.
3. To completely block contact with unmanaged users, under Teams accounts not managed by an organization, set People in my organization can communicate with Teams users whose accounts aren't managed by an organization to Off.
4. To allow contact with unmanaged users only if the internal user initiates the contact:
   1. Under Teams accounts not managed by an organization, set People in my organization can communicate with Teams users whose accounts aren't managed by an organization to On.
   2. Clear the check next to External users with Teams accounts not managed by an organization can contact users in my organization.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

This will vary depending on the organization and need for external collaboration with users not managed by an organization. A formal process for adding external domains for collaboration should be established so that end users have a place to request new external participants.

{% hint style="info" %}
Tips

Make sure its clear how end-users request external collaboration participants
{% endhint %}

## PowerShell Scripts

Set External Access Policy: [Set-CsExternalAccessPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)

## Videos

None Currently
