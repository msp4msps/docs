# Non-admin users shall be prevented from providing consent to 3rd party applications

## Description

Ensure that only administrators can consent to third-party applications and only administrators can control which permissions are granted. An admin consent workflow can be configured in Azure AD; otherwise, users will be blocked when they try to access an application that requires permissions to access organizational data. Develop a process for approving and managing third-party applications.

## Policy

* Only administrators SHALL be allowed to consent to third-party applications.
* An admin consent workflow SHALL be configured.
* Group owners SHALL NOT be allowed to consent to third-party applications.

## Licensing Considerations

This setting can be configured with any Microsoft licensing.

## Set Up Instructions

1. In the Azure Portal, navigate to **Azure Active Directory**.
2. Create a **new Azure AD Group** that contains admin users responsible for reviewing and adjudicating app requests.
3. Under **Manage,** select **Enterprise Applications.**
4. Under Security, select **Consent and permissions**
5. Under User consent for applications, select **Do not allow user consent.**
6.  Under Group owner consent for apps accessing data, select **Do not allow group owner**

    **consent.**
7. In the menu, navigate back to **Enterprise Applications.**
8. Under Manage, select **User Settings.**
9. Under Admin consent requests -> Users can request admin consent to apps they are unable to consent to, **select Yes.**
10. Under Who can review admin consent requests, **select the group created in step two** that is responsible for reviewing and adjudicating app requests.
11. Click **Save.**

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

The number of times a user should be trying to consent a 3rd part application should be low but when they do, they will be blocked. If you have configured the admin consent flow, they will be notified accordingly. This setting is not generally something that requires any communication before turning on.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Automating with PowerShell: Setting up application consent (cyberdrain.com)](https://www.cyberdrain.com/automating-with-powershell-setting-up-application-consent/)

[Monitoring with PowerShell: Monitoring oAuth application changes (cyberdrain.com)](https://www.cyberdrain.com/monitoring-with-powershell-monitoring-oauth-application-changes/)

## Videos

{% embed url="https://www.youtube.com/watch?v=WVNvoiA_ktw" %}
