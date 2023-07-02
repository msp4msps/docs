---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Automatic Forwarding to External Domains SHALL Be Disabled

## Description

This control is intended to prevent bad actors from using client-side forwarding rules to exfiltrate data to external recipients.

## &#x20;Policy

* Automatic forwarding to external domains SHALL be disabled

## Licensing Considerations

Any tenant with an Exchange Online license can configure this setting.

## Set Up Instructions&#x20;

To disallow automatic forwarding to external domains:

1. Sign in to the Exchange admin center.
2. Select Mail flow, then Remote domains.
3. Select Default.
4. Under Email reply types, select Edit reply types.
5. Clear the checkbox next to Allow automatic forwarding, then click Save.



## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

With this setting enabled, users will be prevented from setting up any auto-forwarding rules to external domains.

{% hint style="info" %}
Tips:

None Curently
{% endhint %}

## PowerShell Scripts

* Block Auto FW: [https://github.com/msp4msps/Security/blob/master/Block%20Auto-FW.ps1](https://github.com/msp4msps/Security/blob/master/Block%20Auto-FW.ps1)
* Block Auto FW Multi-Tenant: [https://github.com/msp4msps/Security/blob/master/Block%20Auto-FW\_All%20Customers.ps1](https://github.com/msp4msps/Security/blob/master/Block%20Auto-FW\_All%20Customers.ps1)

## Videos

{% embed url="https://www.youtube.com/watch?v=kskBq4b2rqo" %}
