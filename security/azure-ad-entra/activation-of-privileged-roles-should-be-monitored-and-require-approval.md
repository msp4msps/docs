# Activation of privileged roles should be monitored and require approval

## Description

Since many cyberattacks leverage privileged access, it is imperative to closely monitor the assignment and activation of the highest privileged roles for signs of compromise. Create alerts to trigger when a highly privileged role is assigned to a user and when a user activates a highly privileged role

Require approval for a user to activate a highly privileged role, such as Global Administrator. This makes it more challenging for an attacker to leverage the stolen credentials of highly privileged users and ensures that privileged access is monitored closely.

## Policy

* Eligible and Permanent privileged role assignments shall trigger an alert
* User activation of the Global Administrator role shall trigger an alert
* Activation of the Global Administrator role should require approval

## Licensing Considerations

Azure AD P2 if using Azure AD PIM. This can be purchased standalone or is part of the following bundles:

* EMS+E5
* Microsoft 365 E5

A 3rd party PAM tool could be used as a substitute.

## Set Up Instructions

{% tabs %}
{% tab title="Monitoring" %}
1. In the Azure Portal, navigate to **Azure AD Privileged Identity Management (PIM).**
2. Under Manage, select Azure AD roles.
3. Under Manage, select Roles. This should bring up a list of all the Azure AD roles managed by the PIM service.
4. Click the Global Administrator role.
5. Click Settings and then click Edit.
6. Click the Notification tab.
7. Under Send notifications when members are assigned as eligible to this role, in the Role  assignment alert -> Additional recipients textbox, enter the email address of the mailbox configured to receive the alerts for this role.
8. Under Send notifications when members are assigned as active to this role, in the Role assignment alert -> Additional recipients textbox, enter the email address of the mailbox configured to receive the alerts for this role.
9. Under Send notifications when eligible members activate this role, in the Role activation alert -> Additional recipients textbox, enter the email address of the mailbox configured to receive the alerts for this role.
10. Click Update.
11. Repeat steps 4 through 10 for each of the other highly privileged roles referenced in the policy section above, with one modification:
    1. When configuring the Send notifications when eligible members activate this role for these other roles, enter an email address of a mailbox that is different from the one used to monitor Global Administrator activations.
{% endtab %}

{% tab title="Approval" %}
1. In the Azure Portal, navigate to Azure AD and create a new group named “Privileged Escalation Approvers.” This group will contain users that will receive role activation approval requests and approve or deny them. Users in this group must, at least, have the permissions provided to the Privileged Role Administrators role to adjudicate requests.
2. In the Azure Portal, navigate to Azure AD Privileged Identity Management (PIM).
3. Under Manage, select Azure AD roles.
4. Under Manage, select Roles. This should bring up a list of all the Azure AD roles managed by the PIM service.
5. Repeat this step for the Privileged Role Administrator role, User Administrator role, and other roles that the agency has designated as highly privileged.
   1. Click the Global Administrator role in the list.
   2. Click Settings.
   3. Click Edit.
   4. Select the Require approval to activate option.
   5. Click Select approvers, select the group Privileged Escalation Approvers, and then click Select.
   6. Click Update.
{% endtab %}
{% endtabs %}

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Impact is limited to users who are eligible to privileged roles which should be a small amount in the organization. These users will have to have someone approve their activation.

{% hint style="info" %}
Tips

A group of users should be assigned for approval vs a single point of contact.

More granular settings can be applied to these roles such as requiring MFA upon activation and requiring a justification reason.
{% endhint %}

## PowerShell Scripts

PowerShell for PIM: [PowerShell for Azure AD roles in PIM - Azure AD - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/powershell-for-azure-ad-roles)

## Videos

{% embed url="https://www.youtube.com/watch?v=JyA2bMeWw5o" %}
