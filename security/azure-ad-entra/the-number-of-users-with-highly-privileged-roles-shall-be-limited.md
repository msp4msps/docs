# The number of users with highly privileged roles shall be limited

## Description

Global Administrator is the highest privileged role in Azure AD because it provides unfettered access to the tenant. Therefore, if a user’s credential with these permissions were to be compromised, it would present grave risks to the security of the tenant. Limit the number of users that are assigned the role of Global Administrator. Assign users to finer-grained administrative roles that they need to perform their duties instead of being assigned the Global Administrator role.

## Policy

* A minimum of two users and a maximum of four users SHALL be provisioned with the Global Administrator role.

## Licensing Considerations

All License models support configuration of roles.

## Set Up Instructions

1. In the Azure Portal, navigate to **Azure Active Directory.**
2. Select **Roles and administrators.**
3. Select the **Global administrator role.**
4. Under Manage, select **Assignments.**
5. Validate that between two to four users are listed.
   1. For those who have Azure AD PIM, they will need to check both the Eligible assignments and Active assignments tabs. There should be a total of two to four users across both of these tabs (not individually).
   2. If any groups are listed, need to check how many users are members of each group and include that in the total count.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Impact is limited to users who have the Global Administrator role. If they do have these roles and you need to reduce the number of admins, you can see what levels of access they require today and give them roles with less permissions.

{% hint style="info" %}
Tips

Leverage PIM (need Azure AD P2 licensing) to provide eligible assignments for privileged roles vs permanent assignments.
{% endhint %}

## PowerShell Scripts

PowerShell for PIM: [PowerShell for Azure AD roles in PIM - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/powershell-for-azure-ad-roles)

365 Admin Report: [Export Office 365 Admin Role Report using PowerShell (o365reports.com)](https://o365reports.com/2021/03/02/Export-Office-365-admin-role-report-powershell/)

## Videos

{% embed url="https://www.youtube.com/watch?v=JyA2bMeWw5o" %}
