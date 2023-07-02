# Browser Sessions shall not be persistent for privileged users

## Description

To reduce the risk of credential theft during user sessions, disallow persistent browser sessions for highly privileged users.

## Policy

* &#x20;Highly privileged users shall not have persistent browser sessions.

## Licensing Considerations

Azure AD P1. Can be purchased standalone or part of the following bundles:

* Microsoft 365 Business Premium
* EMS+ E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5



## Set Up Instructions

1. Create a conditional access policy for Persistent Browser sessions: [Configure authentication session management - Azure Active Directory - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#policy-2-persistent-browser-session)
2. Under Users>Include\<Select Users and Groups, choose Directory Roles.
3. Configure highly privileged Directory Roles

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

Since this will be only scoped to privileged roles, the impact will be limited. The severity of impact is increased to medium since it does require the scoped users to reauthenticate once every time the user closes and reopens the browser.

{% hint style="info" %}
Tips

This is a policy that you could scope additionally to guest users and for external access on personal devices that are not MDM or MAM enrolled.
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

None Currently
