# Inbound Anti-Spam Protections SHALL Be Enabled

## Description

There are several features that protect against inbound spam: bulk compliant level, quarantines, safety tips, and zero hour auto purge.

## Policy

* The bulk complaint level (BCL) threshold SHOULD be set to six or lower.
* Spam and high confidence spam SHALL be moved to either the junk email folder or the quarantine folder.
* Phishing and high confidence phishing SHALL be quarantined.
* Bulk email SHOULD be moved to either the junk email folder or the quarantine folder.
* Spam in quarantine SHOULD be retained for at least 30 days.
* Spam safety tips SHOULD be turned on.
* Zero-hour auto purge (ZAP) SHALL be enabled for both phishing and spam messages.
* Allowed senders MAY be added, but allowed domains SHALL NOT be added.
* The previously listed configurations SHALL be set in the default policy and SHOULD be set in all existing custom policies.

## Licensing Considerations

• This setting can be configured with any tenant that has Exchange Online.

## Set Up Instructions

[Configure spam filter policies - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spam-policies-configure?view=o365-worldwide)

[Microsoft recommendations for EOP and Defender for Office 365 security settings - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365?view=o365-worldwide#eop-anti-spam-policy-settings)

1. Sign in to Microsoft 365 Defender.
2. Under Email & collaboration, select Policies & rules.
3. Select Threat policies.
4. Under Policies, select Anti-spam.
5. Select Anti-spam inbound policy (Default).
6. Under Bulk email threshold & spam properties, click Edit spam threshold and properties.
7. Set Bulk email threshold to six or lower.
8. Click Save.
9. Under Actions, click Edit actions.
10. In the Message actions section:
    1. For Spam, High confidence spam, and Bulk, set the action to either Move message to Junk Email folder or Quarantine message.
    2. Set the action for both Phishing and High confidence phishing to Quarantine message.
    3. Set Retain spam in quarantine for this many days to “30.”
    4. Check Enable spam safety tips.
    5. Check Enable zero-hour auto purge (ZAP), Enable for phishing messages, and Enable for spam messages.
11. Click Save

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

With this setting in place, its possible that false positives will be generated and users will need to look either in their junk folder or have an admin release a message from quarantine that is legitimate.

{% hint style="info" %}
Tips

• Educate users on how to make request for quarantined messages to be released
{% endhint %}

## PowerShell Scripts

[Configure spam filter policies - Office 365 | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spam-policies-configure?view=o365-worldwide#use-powershell-to-create-anti-spam-policies)

## Videos

{% embed url="https://www.youtube.com/watch?v=7_ILTL2QAu0" %}
