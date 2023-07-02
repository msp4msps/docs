# Windows and MacOS devices should be prevented from syncing the OneDrive Client on personal devices

## Description

Windows and MacOS devices should be prevented from syncing the OneDrive Client on devices that are personally owned. These devices may not be joined to the corporate domain and have a highly likelihood of being compromised without the corporations security implemented.

## Policy

* OneDrive Client Sync for Windows and MacOS SHALL be restricted to corporate owned devices.

## Licensing Considerations

Any tenant with OneDrive for Business licensing can access this setting.

## Set-Up Instructions

[Allow syncing only on computers joined to specific domains - SharePoint in Microsoft 365 | Microsoft Learn](https://learn.microsoft.com/en-us/sharepoint/allow-syncing-only-on-specific-domains)

[SharePoint and OneDrive unmanaged device access controls for administrators - SharePoint in Microsoft 365 | Microsoft Learn](https://learn.microsoft.com/en-us/sharepoint/control-access-from-unmanaged-devices)

1. Open the SharePoint admin center.
2. In the left-hand navigation pane, select Settings and sign in with an account that has admin permissions for the agency.
3. Select Sync.
4. Select the Allow syncing only on computers joined to specific domains check box.
5. Add the Globally Unique Identifier (GUID) of each domain for the member computers that the agency wants to be able to sync.
   1. Note: Add the domain GUID of the computer domain membership. If users are in a separate domain, only the domain GUID that the computer account is joined to is required.
   2. Important: This setting is only applicable to Active Directory domains. It does not apply to Azure Active Directory (AAD) domains. If agency devices are only Azure AD joined, consider using a Conditional Access Policy instead.
6. Click Save

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

Users will be prevented from syncing OneDrive or a SharePoint site to their local device if that device is not corporate owned.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Set-SPOTenantSyncClientRestriction (Microsoft.Online.SharePoint.PowerShell) | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction?view=sharepoint-ps#:%7E:text=In%20order%20to%20explicitly%20block%20Microsoft%20OneDrive%20client,cmdlet%20with%20the%20BlockMacSync%20parameter%20set%20to%20true.?msclkid=f80f95c5c4c611ecac7de0980370f33c)

## Videos&#x20;

{% embed url="https://www.youtube.com/watch?v=1wauXYlGGJI" %}



