# Passwords shall not expire

## Description

Ensure that user passwords do not expire. Both the National Institute of Standards and Technology (NIST) and Microsoft emphasize MFA because they indicate that mandated password changes make user accounts less secure.

## Policy

* &#x20;User passwords shall not expire

## Licensing Considerations

Configuring this setting is available in any Microsoft 365 offering.

## Set Up Instructions

1.  Follow [these steps](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/set-password-expiration-policy?view=o365-worldwide#set-password-expiration-policy) to set passwords to never expire


2. Microsoft Password Guidance [Microsoft\_Password\_Guidance-1.pdf](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/06/Microsoft\_Password\_Guidance-1.pdf)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

Impact is medium as users do not have to reset their passwords on a periodic basis but will have to set up passwordless methods of authentication such as Microsoft Authentication.&#x20;

{% hint style="info" %}
Tips

Ensure that weak passwords are not being used [Password protection in Azure Active Directory - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/authentication/concept-password-ban-bad)

If possible, think about going passwordless: [Passwordless authentication | Microsoft Security](https://www.microsoft.com/en-us/security/business/solutions/passwordless-authentication?rtc=1)
{% endhint %}

## PowerShell Scripts

[Automating with PowerShell: Deploying passwordless Authentication (cyberdrain.com)](https://www.cyberdrain.com/automating-with-powershell-deploying-passwordless-authentication/)

## Videos

{% embed url="https://www.youtube.com/watch?v=OjfdFPIu2KI" %}

{% embed url="https://www.youtube.com/watch?v=hpzHqKFINMg" %}

{% embed url="https://www.youtube.com/watch?v=RpX7JgexdwA" %}
