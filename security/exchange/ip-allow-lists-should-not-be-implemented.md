# IP Allow Lists SHOULD NOT be Implemented

## Description

Microsoft Defender supports the creations of IP “allow lists,” which are intended to ensure that emails from specific senders are not blocked. However, as a result, emails from these senders bypass important security mechanisms, such as spam filtering, SPF, DKIM, DMARC, and FROM address enforcement.

IP “block lists” ensure that mail from these IP addresses is always blocked. Although we have no specific guidance on which IP addresses to add, block lists can be used to block mail from known spammers. The IP “safe lists” group is a dynamic list of “known, good senders,” which Microsoft sources from various third-party subscriptions. As with senders in the allow list, emails from these senders bypass important security mechanisms.

## Policy

* IP allow lists SHOULD NOT be created.
* Safe lists SHOULD NOT be enabled.
* A connection filter MAY be implemented to create an IP “block list.”

## Licensing Considerations

• Exchange Online Protection

## Set Up Instructions

[Create safe sender lists - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide#use-the-ip-allow-list)

[Configure the default connection filter policy - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/connection-filter-policies-configure?view=o365-worldwide)

To modify the connection filters, follow the instructions found on Use the Microsoft 365 Defender portal to modify the default connection filter policy.

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Under Policies, select Anti-spam.
4. Select Connection filter policy (Default).
5. Click Edit connection filter policy.
6. Ensure no addresses are specified under Always allow messages from the following IP addresses or address range.
7. Enter addresses under Always block messages from the following IP addresses or address range as needed.
8. Ensure Turn on safe list is not selected.

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

With this setting in place, there may be some false positives from IP addresses that are seen as malicious.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Configure the default connection filter policy - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/connection-filter-policies-configure?view=o365-worldwide#use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy)

## Videos

{% embed url="https://www.youtube.com/watch?v=cw2O093bubg" %}
