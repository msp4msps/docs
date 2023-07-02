# High Risk Users Shall Be Blocked

## Description

Azure AD Identity Protection uses various signals to detect the risk level for each user and determine if an account has likely been compromised. Users who are determined to be high risk are to be blocked from accessing the system via Conditional Access until an administrator remediates their account.

## Policy

* Users detected as high risk shall be blocked.
* Notifications will be sent to admins when high-risk users are detected.

## Licensing Considerations

Azure AD P2. Can be purchased standalone or part of the following bundles:

* EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5



## Set Up Instructions

1. Create a conditional access policy for Sign-In risk: [Risk policies - Azure Active Directory Identity Protection - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/identity-protection/howto-identity-protection-configure-risk-policies)
2. Under Access Controls> Grant, select Block Access
3. To Create notifications for admins: [Azure Active Directory Identity Protection notifications - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/identity-protection/howto-identity-protection-configure-notifications)

Identity Protection Overview: [Azure Active Directory Identity Protection notifications - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/identity-protection/howto-identity-protection-configure-notifications)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:red;">High</mark>
{% endhint %}

Once a respective conditional access policy is implemented, if a high-risk user attempts to login, the user will receive an error message with instructions to contact the administrator to re-enable their access.

<div align="left">

<figure><img src="../../.gitbook/assets/pic3.png" alt=""><figcaption></figcaption></figure>

</div>

{% hint style="info" %}
Tips

Integrate the notifications into your ticketing system vs a single administrator.

Investigate the risk event following these steps: [Investigate risk Azure Active Directory Identity Protection - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/identity-protection/howto-identity-protection-investigate-risk)
{% endhint %}

## PowerShell Scripts

Conditional Access Policies as Code: [Azure-Samples/azure-ad-conditional-access-apis: Use Conditional Access Graph APIs to manage policies like code. Automate approvals to promote policies from preproduction environments, backup and restore, monitor change, and plan ahead for emergencies. (github.com)](https://github.com/Azure-Samples/azure-ad-conditional-access-apis)

## Videos

{% embed url="https://www.youtube.com/watch?v=BychSG4bJDY" %}

{% embed url="https://www.youtube.com/watch?v=Nx2ych3xHl0" %}

{% embed url="https://www.youtube.com/watch?v=QovweNBIp-A" %}
