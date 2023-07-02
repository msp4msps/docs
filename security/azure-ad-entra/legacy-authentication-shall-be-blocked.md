# Legacy Authentication shall be blocked

## Description

Block legacy authentication protocols using a conditional access policy. Legacy authentication does not support multifactor authentication (MFA), which is required to minimize the impact of user credential theft.

## Policy

* Legacy Authentication shall be blocked.

## Licensing Considerations

Enabling a conditional access policy to block legacy authentication requires an Azure AD P1 license which can be purchased standalone or through the following common plans:

* Microsoft 365 Business Premium
* EMS + E3 or EMS + E5
* Microsoft 365 E3
* Microsoft 365 E5

Legacy Auth can be blocked by enabling Security Defaults which does not require an Azure AD P1 license and can be used with any Microsoft licensing model

## Set Up Instructions

1. Before enabling the policy, you can [review if there is any authentication in use.](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/block-legacy-authentication#identify-legacy-authentication-use)
2. Create a Conditional Access Policy with the [Templates available](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common#conditional-access-templates-preview)
3. Chose the “Block Legacy Authentication” setting
4. Modify the policy to ensure your emergency access user/group is excluded

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

The level of impact here will vary by organization depending on the use of legacy authentication. It is possible there will be no impact at all if no legacy authentication protocols are in use. If there are some in use like IMAP/POP, there would be significant end-user impact. Its best to leverage the sign-in logs as mentioned in the previous section to identify any legacy authentication present and take proactive steps on remediation.

{% hint style="info" %}
Tips

Turn the Conditional Access Policy to “Report-Only” mode to get information around how many users in the organization this will impact before turning the policy on.

Viewing legacy auth sign-ins within Azure AD: [Identify legacy authentication use – Practice Protect Support](https://support.practiceprotect.com/knowledge-base/identify-legacy-authentication-use/?doing\_wp\_cron=1678631042.2050209045410156250000)
{% endhint %}

## PowerShell Scripts

Basic Auth Reporting [msp4msps/Basic-Authentication-Reporting (github.com)](https://github.com/msp4msps/Basic-Authentication-Reporting)

## Videos

{% embed url="https://www.youtube.com/watch?v=mb7At6B_8p0&t" %}

{% embed url="https://www.youtube.com/watch?v=E-qPLCc5O9M" %}
