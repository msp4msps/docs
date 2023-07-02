# Authorized Applications shall be configured for Single Sign-On

## Description

If available, all authorized applications should be configured for single sign-on to extend authentication security to 3rd party applications.

## Policy

* Authorized applications shall be configured for single sign-on if available.

## Licensing Considerations

To configure Enterprise applications for SSO, an Azure AD P1 license is required. This can be purchased standalone or is available as part of the following bundles:

* Microsoft 365 Business Premium
* EMS+ E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

The configuration settings will be application specific but all applications will be configured in the Enterprise application section of Azure AD: [Enable single sign-on for an enterprise application - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/manage-apps/add-application-portal-setup-sso)

Example SSO with Dropbox: [Tutorial: Azure Active Directory integration with Dropbox Business - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/saas-apps/dropboxforbusiness-tutorial)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

After applications are set up for single sign-on, users will be able to leverage their Azure Active Directory credentials to access the application. It is important to alert users before turning on SSO for an application so they are not caught off-guard from a redirection to Microsoft when trying to sign-in. Be careful with some applications as you can get locked out if settings are not configured properly.

{% hint style="info" %}
Tips

Establish a communication plan prior to setting up SSO for an application.

Leverage Azure AD groups to grant and revoke access to applications.

Leverage SCIM provisioning if it is available from the application provider.
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

{% embed url="https://www.youtube.com/watch?v=7SU5S0WtNNk" %}

{% embed url="https://www.youtube.com/watch?v=pVO30oYK0AM" %}

{% embed url="https://www.youtube.com/watch?v=iFs0xN8YI68" %}
