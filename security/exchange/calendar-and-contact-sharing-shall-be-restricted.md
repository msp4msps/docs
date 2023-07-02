# Calendar and Contact Sharing SHALL Be Restricted

## Description

Exchange Online allows the creation of sharing polices that ease default restrictions on contact and calendar details sharing. These policies should only be enabled with caution and must comply with the following policies.

## Policy

* Contact folders SHALL NOT be shared with all domains, although they MAY be shared with specific domains.
* Calendar details SHALL NOT be shared with all domains, although they MAY be shared with specific domains

## Licensing Considerations

This setting can be configured in any Microsoft tenant.

## Set Up Instructions

[Sharing policies in Exchange Online | Microsoft Learn](https://learn.microsoft.com/en-us/exchange/sharing/sharing-policies/sharing-policies)

[Sharing in Exchange Online | Microsoft Learn](https://learn.microsoft.com/en-us/exchange/sharing/sharing)

To restrict sharing with all domains:

1. Sign in to the Exchange admin center.
2. Under Organization, select Sharing.
3. Under Individual Sharing, for all existing policies, ensure that for all sharing rules, Sharing with all domains is not selected.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

With this setting in place, users will not be able to share calendar or contacts to any external domains unless they are whitelisted. A formal request process should be put into place and evaluated when a user needs to share their calendar details.



{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

Free/Busy Sharing Settings: [https://github.com/msp4msps/Security/blob/master/Free\_Busy%20Calendar%20Settings-Single%20Tenant.ps1](https://github.com/msp4msps/Security/blob/master/Free\_Busy%20Calendar%20Settings-Single%20Tenant.ps1)

Free/Busy Sharing Settings (Multi-Tenant): [https://github.com/msp4msps/Security/blob/master/Free\_Busy%20Calendar%20Settings%20Multitenant.ps1](https://github.com/msp4msps/Security/blob/master/Free\_Busy%20Calendar%20Settings%20Multitenant.ps1)

## Videos

None Currently
