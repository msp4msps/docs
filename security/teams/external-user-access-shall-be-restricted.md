# External User Access SHALL Be Restricted

## Description

External access allows external users to look up internal users by their email address to initiate chats and calls entirely within Teams. Blocking external access prevents external users from using Teams as an avenue for reconnaissance or phishing. Even with external access disabled, external users will still be able to join Teams calls, assuming anonymous join is enabled. Depending on organizational need, if both external access and anonymous join need to be blocked— neither required nor recommended by this baseline—external collaborators would only be able to attend meetings if added as a B2B guest user. External access may be granted on a per-domain basis. This may be desirable in some cases, e.g., for agency-to-agency collaboration.

## Policy

* External access SHALL only be enabled on a per-domain basis.
* Anonymous users SHOULD be enabled to join meetings.

## Licensing Considerations

Any Teams licensing supports this configuration.

## Set Up Instructions

{% tabs %}
{% tab title="Microsoft Resources" %}
[Manage external meetings and chat - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/manage-external-access)

[Manage meeting settings - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

[Use guest access and external access to collaborate with people outside your organization - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/communicate-with-users-from-other-organizations)
{% endtab %}

{% tab title="Enable External Access for Specific Domains" %}
1. Sign in to the Microsoft Teams admin center.
2. Select Users -> External access.
3. Under Choose which external domains your users have access to, select Allow only specific external domains.
4. Click Allow domains to add allowed external domains. All domains not added in this step will be blocked.
5. Click Save
{% endtab %}

{% tab title="Enable Anonymous users to Join Meetings" %}
1. Sign in to the Microsoft Teams admin center.
2. Select Meetings -> Meeting settings.
3. Under Participants, set Anonymous users can join a meeting to On.
4. Click Save
{% endtab %}

{% tab title="Per Policy" %}
Anonymous users can also be enabled/blocked on a per-policy basis.

1. Sign in to the Microsoft Teams admin center.
2. Select Meetings -> Meeting policies.
3. Select the Global (Org-wide default), or other policy as needed.
4. Under Participants & guests, set Let anonymous people join a meeting to On.
5. Click Save.
{% endtab %}
{% endtabs %}

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

This will vary depending on the organization and need for external collaboration. A formal process for adding external domains for collaboration should be established so that end users have a place to request new external participants.

{% hint style="info" %}
Tips

Make sure its clear how end-users request external collaboration participants
{% endhint %}

## PowerShell Scripts

Set External Access Policy: [Set-CsExternalAccessPolicy (SkypeForBusiness) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)

[Manage external meetings and chat - Microsoft Teams | Microsoft Learn](https://learn.microsoft.com/en-us/microsoftteams/manage-external-access#limit-external-access-to-specific-people)

## Videos

None Currently
