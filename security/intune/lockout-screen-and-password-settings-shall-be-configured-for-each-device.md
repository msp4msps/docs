# Lockout screen and password settings shall be configured for each device

## Description

Lockout screen timeouts should be configured for a certain number of minutes of activity for all device platforms. Password complexity requirements should be enforced and users should be prompted to change their password if it does not meet corporate requirements. In Intune, the location to configure these settings varies depending on the platform.

**Windows**: Security Baselines (Device Lock, Local Policies Security Options), Configuration Profiles (Device Restrictions: Password)

**macOS**: Compliance Policy (System Security)

**iOS**: Compliance Policy (System Security)

**Android**: Compliance Policy (System Security)

## Policy

* All supported devices have configuration settings defined/enforced for lockout screen timeouts and passwords

## Licensing Considerations

• Any tenant with Intune licensing can access this setting.

## Set-Up Instructions

Windows Security Baselines: [Create security baseline profiles in Microsoft Intune | Microsoft Learn](https://learn.microsoft.com/en-us/mem/intune/protect/security-baselines-configure#create-the-profile)

1. Under Device Lock set the password requirements
2. Under Local Policies Security Options, Set the Minutes of lock screen inactivity until screen save activates policy

macOS Compliancy Policy: [macOS device compliance settings in Microsoft Intune | Microsoft Learn](https://learn.microsoft.com/en-us/mem/intune/protect/compliance-policy-create-mac-os)

1. Under System Security, modify the Password requirements and minutes of inactivity before password required

iOS Compliancy Policy: [iOS/iPadOS device compliance settings in Microsoft Intune | Microsoft Learn](https://learn.microsoft.com/en-us/mem/intune/protect/compliance-policy-create-ios)

1. Under System Security, modify the Password requirements and minutes of inactivity before password required

Android Compliancy Policy: [Android Enterprise compliance settings in Microsoft Intune | Microsoft Learn](https://learn.microsoft.com/en-us/mem/intune/protect/compliance-policy-create-android-for-work)

1. Under System Security, modify the Password requirements and minutes of inactivity before password required

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

End users who enroll devices into Intune after this policy is enforced may be prompted to update their password if the policy requirements are not met on the device.\


{% hint style="info" %}
Tips

Make sure you don’t have conflicting policies between configuration profiles, security baselines, and compliance policies
{% endhint %}

## PowerShell Scripts

[powershell-intune-samples/CompliancePolicy at master · microsoftgraph/powershell-intune-samples (github.com)](https://github.com/microsoftgraph/powershell-intune-samples/tree/master/CompliancePolicy)

[powershell-intune-samples/DeviceConfiguration at master · microsoftgraph/powershell-intune-samples (github.com)](https://github.com/microsoftgraph/powershell-intune-samples/tree/master/DeviceConfiguration)

## Videos&#x20;

{% embed url="https://www.youtube.com/watch?v=ZU1UKWavXIg" %}

{% embed url="https://www.youtube.com/watch?v=JhfecIfBn2c" %}
