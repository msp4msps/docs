# MFA is enforced on accounts with Highly Privileged Roles

## Description

Require users to perform MFA to access highly privileged roles. This configuration provides a backup policy to enforce MFA for highly privileged users in case the main conditional access policy—which requires MFA for all users—is disabled or misconfigured.

## Policy

* MFA shall be required for users to access highly privileged roles
* Highly Privileged roles include the following:
  * Global Administrator
  * Privileged Role Administrator
  * User Administrator
  * SharePoint Administrator
  * Exchange Administrator
  * Hybrid Identity Administrator
  * Application Administrator
  * Teams Administrator
* One emergency access account shall be excluded from the MFA policy

## Licensing Considerations

Enforcing MFA for privileged roles through conditional access requires an Azure AD P1 license which can be purchased standalone or through the following common plans:

o   Microsoft 365 Business Premium

o   EMS + E3 or EMS + E5

o   Microsoft 365 E3

o   Microsoft 365 E5

## Set Up Instructions

1\. Create a Conditional Access Policy with the [Templates:  available](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common#conditional-access-templates-preview)

2\. Chose the “Require Multi-Factor authentication for Admins” setting

3\. Modify the policy to ensure your emergency access user/group is excluded

## End-User Impact&#x20;

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

End-User impact is low due to this policy scoped to a small set of users. The end-user experience is the same as the previous section. The user experience will vary depending on which MFA methods you have set up.

{% hint style="info" %}
Tips

* Create a group in Azure Active Directory used to place all accounts excluded from MFA. This would be your emergency break-glass account and a service accounts such as the Azure AD Connect sync service account.
* If you are able to enforce phishing-resistant MFA across all users, at minimum try to enable it for accounts with privileged roles (Global Admins, User Admins, etc.)
* Turn the Conditional Access Policy to “Report-Only” mode to get information around how many users in the organization this will impact before turning the policy on.
{% endhint %}

## PowerShell Scripts

Viewing Global Admins without MFA: [Security/Customer-Global Admin without MFA.ps1 at master · msp4msps/Security (github.com)](https://github.com/msp4msps/Security/blob/master/Customer-Global%20Admin%20without%20MFA.ps1)

Conditional Access Policies as Code: [Azure-Samples/azure-ad-conditional-access-apis: Use Conditional Access Graph APIs to manage policies like code. Automate approvals to promote policies from preproduction environments, backup and restore, monitor change, and plan ahead for emergencies. (github.com)](https://github.com/Azure-Samples/azure-ad-conditional-access-apis)

## Videos

{% embed url="https://www.youtube.com/watch?v=DFwERh9Xxk0" %}
