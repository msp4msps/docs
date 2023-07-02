# Simple Mail Transfer Protocol Authentication SHALL Be Disabled

## Description

Modern email clients that connect to Exchange Online mailboxes—including Outlook, Outlook on the web, iOS Mail, and Outlook for iOS and Android—do not use Simple Mail Transfer Protocol Authentication (SMTP AUTH) to send email messages. SMTP AUTH is only needed for applications outside of Outlook that send email message.

## Policy

* SMTP AUTH SHALL be disabled in Exchange Online
* SMTP AUTH MAY be enabled on a per-mailbox basis

## Licensing Considerations

This setting can be configured in any Microsoft tenant.



## Set Up Instructions

SMTP AUTH can only be disabled tenant-wide using Exchange Online PowerShell. To do so, follow the instructions listed at [Disable SMTP AUTH in your organization | Microsoft Docs.](https://docs.microsoft.com/en-us/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission#disable-smtp-auth-in-your-organization)

To enable SMTP AUTH on a per-mailbox basis, follow the instructions listed at [Use the Microsoft 365 admin center to enable or disable SMTP AUTH on specific mailboxes | Microsoft Docs.](https://docs.microsoft.com/en-us/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission#use-the-microsoft-365-admin-center-to-enable-or-disable-smtp-auth-on-specific-mailboxes)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

This will vary depending on the organization and what existing mail infrastructure looks like. This can be impactful if you have scanners, printers, or Line-of-business (LOB) applications leveraging SMTP auth for message relay. To avoid any issues here, [follow these steps.](https://learn.microsoft.com/en-us/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365)

{% hint style="info" %}
Tips

Use the following for configuring SMTP relay for printers, scanners, etc: [How to set up a multifunction device or application to send email using Microsoft 365 or Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365)
{% endhint %}

## PowerShell Scripts

Changing Modern Auth Settings: [https://www.cyberdrain.com/automating-with-powershell-changing-modern-and-basic-authentication-settings/](https://www.cyberdrain.com/automating-with-powershell-changing-modern-and-basic-authentication-settings/)

Basic Auth Reporting: [https://github.com/msp4msps/Basic-Authentication-Reporting](https://github.com/msp4msps/Basic-Authentication-Reporting)

## Videos

{% embed url="https://www.youtube.com/watch?v=xbR0MUgCPa4" %}
