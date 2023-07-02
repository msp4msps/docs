# Managed Devices shall be required for authentication

## Description

Require that users connect to M365 from a device that is managed using conditional access. Companies that are implementing a hybrid Azure AD environment will likely use the conditional access control option named Hybrid Azure AD joined, whereas companies that are using devices that connect directly to the cloud and do not join an on-premises AD will use the conditional access control option named, Require device to be marked as compliant.

Guest user access note: This conditional access policy will impact guest access to the tenant because guest users will be required to authenticate from a managed device similar to regular Azure AD users. For guest users, the organization that manages their home tenant is responsible for managing their devices and the resource tenant must be configured to trust the device claims from the home tenant, otherwise guest users will be blocked by the policy. [This link describes the detailed authentication flow for guest users and how conditional access related to devices is applied](https://docs.microsoft.com/en-us/azure/active-directory/external-identities/authentication-conditional-access). The implementation section describes the cross-tenant settings that must be configured in both the home and the resource tenants to facilitate guest access with managed devices.

## Policy

* &#x20;Managed Devices shall be required for authentication.

## Licensing Considerations

Azure AD P1 & Microsoft Intune. Can be purchased standalone or part of the following bundles:

* Microsoft 365 Business Premium
* EMS+ E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

1. Create a conditional access policy to require devices to be marked as compliant in order to gain access [Require compliant, hybrid joined devices, or MFA - Azure Active Directory - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device#create-a-conditional-access-policy)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:red;">High</mark>
{% endhint %}

Users will not be able to login to their account on devices not enrolled into Intune and in a “Compliant” state.

{% hint style="info" %}
Tips

Have a plan for guest users in the organization. Follow the steps as linked in the summary section or exclude guest users from the policy.
{% endhint %}

## PowerShell Scripts

None Currently

## Videos

{% embed url="https://www.youtube.com/watch?v=Vjhn5GoMPOI" %}
