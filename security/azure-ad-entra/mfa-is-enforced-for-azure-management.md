# MFA is enforced for Azure Management

## Description

Organizations use many Azure services and manage them from Azure Resource Manager based tools like:

* Azure portal
* Azure PowerShell
* Azure CLI

These tools can provide highly privileged access to resources that can make the following changes:

* Alter subscription-wide configurations
* Service settings
* Subscription billing

To protect these privileged resources, Microsoft recommends requiring multifactor authentication for any user accessing these resources. This configuration provides a backup policy to enforce MFA for users accessing Azure Resources in case the main conditional access policy—which requires MFA for all users—is disabled or misconfigured.

## Policy

* MFA shall be required for users to access Azure Resources
* One emergency access account shall be excluded from the MFA policy

## Licensing Considerations

Enforcing MFA for Azure Management through conditional access requires an Azure AD P1 license which can be purchased standalone or through the following common plans:

* Microsoft 365 Business Premium
* EMS + E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

1. Create a Conditional Access Policy with the [Templates available](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common#conditional-access-templates-preview)
2. Chose the “Require Multi-Factor authentication for Azure Management” setting
3. Modify the policy to ensure your emergency access user/group is excluded

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>&#x20;
{% endhint %}

End-User impact is low due to this policy scoped to a small set of users. The end-user experience is the same as the previous section. The user experience will vary depending on which MFA methods you have set up. Below you will find links to end-user communication templates that help for various rollout scenarios.

{% hint style="info" %}
Tips

Create a group in Azure Active Directory used to place all accounts excluded from MFA. This would be your emergency break-glass account and a service accounts such as the Azure AD Connect sync service account.



Turn the Conditional Access Policy to “Report-Only” mode to get information around how many users in the organization this will impact before turning the policy on.
{% endhint %}

## PowerShell Scripts

Conditional Access Policies as Code: [Azure-Samples/azure-ad-conditional-access-apis: Use Conditional Access Graph APIs to manage policies like code. Automate approvals to promote policies from preproduction environments, backup and restore, monitor change, and plan ahead for emergencies. (github.com)](https://github.com/Azure-Samples/azure-ad-conditional-access-apis)

## Videos

{% embed url="https://www.youtube.com/watch?v=nSoAnFhDm9s&t" %}
