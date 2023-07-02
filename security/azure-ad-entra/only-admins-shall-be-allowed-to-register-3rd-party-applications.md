# Only Admins shall be allowed to register 3rd party applications

## Description

Ensure that only administrators can register third-party applications that can access the tenant.

## Policy

* Only administrators SHALL be allowed to register third-party applications.

## Licensing Considerations

This setting can be configured with any Microsoft licensing.

## Set Up Instructions

1. In the Azure Portal, navigate to Azure Active Directory.
2. Under **Manage,** select **Users.**
3. Select **User settings.**
4. Under App Registrations -> Users can register applications, select **No.**
5. Click **Save.**

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

The number of times a user should be trying to register a 3rd part application should be low but when they do, they will be blocked. This setting is not generally something that requires any communication before turning on.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Automating with PowerShell: Setting up application consent (cyberdrain.com)](https://www.cyberdrain.com/automating-with-powershell-setting-up-application-consent/)

[Monitoring with PowerShell: Monitoring oAuth application changes (cyberdrain.com)](https://www.cyberdrain.com/monitoring-with-powershell-monitoring-oauth-application-changes/)

## Videos

{% embed url="https://www.youtube.com/watch?v=WVNvoiA_ktw" %}
