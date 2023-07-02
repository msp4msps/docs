# Highly privileged role assignments shall be periodically reviewed

## Description

Access reviews should be periodically performed for users with permanent or eligible privileged roles. Users should evaluate whether they still need these permissions and update assignments accordingly. Access reviews can be performed manually or with a tool like [Microsoft Access Reviews](https://learn.microsoft.com/en-us/azure/active-directory/governance/access-reviews-overview) which is part of an Azure AD P2 subscription.

## Policy

* &#x20;Access reviews shall be performed for users with permanent or eligible privileged roles.

## Licensing Considerations

To leverage the Access Reviews in Microsoft, an Azure AD P2 license is required. This can be purchased standalone or as part of the following bundles:

* EMS + E5
* Microsoft 365 E5

## Set Up Instructions

1. Follow [these steps](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-create-azure-ad-roles-and-resource-roles-review?toc=%2Fazure%2Factive-directory%2Fgovernance%2Ftoc.json) to create Access Reviews leveraging the native tooling in Microsoft.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Impact is limited to the users with privileged roles. When an access review is conducted, the user will be notified via email to review their existing roles. They will be able to provide feedback on if they need to continue to have that role with a justification reason.

{% hint style="info" %}
Tips

Try to perform access reviews on a semi-annual basis at the minimum.
{% endhint %}

## PowerShell Scripts

365 Admin Report: [Export Office 365 Admin Role Report using PowerShell (o365reports.com)](https://o365reports.com/2021/03/02/Export-Office-365-admin-role-report-powershell/)

Access Reviews PowerShell samples: [microsoft/access-reviews-samples: This repo contains sample code that demonstrates programmatic access to Azure AD Access Reviews. Sample code includes reading and managing Access Reviews, as well as working on decisions and results of Access Reviews. (github.com)](https://github.com/microsoft/access-reviews-samples)

## Videos

{% embed url="https://www.youtube.com/watch?v=rsKuvjK7U4A" %}
