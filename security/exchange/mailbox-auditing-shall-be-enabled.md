# Mailbox Auditing SHALL Be Enabled

## Description

Mailbox auditing helps users investigate compromised accounts or discover illicit access to Exchange Online. Some actions performed by administrators, delegates, and owners are logged automatically. While mailbox auditing is enabled by default, organizations should ensure that it has not been inadvertently disabled.

## Policy

* Mailbox auditing SHALL be enabled

## Licensing Considerations

• Exchange Online Protection

## Set Up Instructions

Mailbox auditing can be enabled from the Exchange Online PowerShell. Follow the

instructions listed on [Manage mailbox auditing in Office 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide).

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">None</mark>
{% endhint %}

There is no end-user impact for this setting

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[https://docs.microsoft.com/en-us/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide](https://docs.microsoft.com/en-us/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide)

To check the current mailbox auditing status via PowerShell:

1. Connect to the Exchange Online PowerShell.
2. Run the following command:

```powershell
Get-OrganizationConfig | Format-List AuditDisabled.
```

To enable mailbox auditing&#x20;

```powershell
Set-OrganizationConfig –AuditDisabled $false.
```

## Videos

{% embed url="https://www.youtube.com/watch?v=CTFuZGoRllw" %}
