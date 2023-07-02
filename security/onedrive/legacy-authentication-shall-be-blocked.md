# Legacy Authentication SHALL Be Blocked

## Description

Modern authentication, based on Active Directory Authentication Library (ADAL) and Open Authorization 2 (OAuth2), is a critical component of security in Office 365. It provides the device authentication and authorization capability of Office 365, which is a foundational security component. If modern authentication is not required, this creates a loophole that could allow unauthorized devices to connect to OneDrive and download/exfiltrate enterprise data. For this reason, it is important to make sure that only apps that support modern authentication are allowed to connect, assuring that only authorized devices are allowed to access enterprise data.

## Policy

* Legacy Authentication SHALL be blocked for OneDrive and SharePoint

## Licensing Considerations

Any tenant with OneDrive for Business licensing can access this setting.

## Set-Up Instructions

1. Open the SharePoint admin center.
2. In the left-hand navigation pane, click Policies > Access Control > Device access.
3. Click Apps that don’t use modern authentication to display the device access settings.
4. On the Apps that don’t use modern authentication page, select the Block access option

**Note to this can be accomplished through a Conditional Access Policy as well**

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:green;">Low</mark>
{% endhint %}

There should not be many users trying to access OneDrive or SharePoint documents with apps that do not use modern authentication.

{% hint style="info" %}
Tips

• If you have a Conditional Access Policy set up to block legacy authentication, this setting is not necessary
{% endhint %}

## PowerShell Scripts

None Currently

## Videos&#x20;

{% embed url="https://www.youtube.com/watch?v=uSXlVVHcv9I&t=839s" %}



