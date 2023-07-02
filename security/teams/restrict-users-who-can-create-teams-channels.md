# Restrict Users who can Create Teams Channels

## Description

Users within a tenant have the ability to create a public or private Teams channel by default. Behind the scenes, creating a Teams channel also creates a Microsoft 365 or Office 365 Group and a SharePoint site with a document library that stores all documents shared within the Teams channel. Over time, if this is not managed, the environment could quickly get out of hand with the number of Teams channels being created. This could lead to data loss, insecure sharing of documentation, and overall confusion across the organization. We recommend limiting the creation of Teams channels to certain members within the organization and creating a formal request process for new channels. To configure this setting, you will be restricting access for who can create a group as that is the backend to a Teams channel.

## Policy

* Creating Teams Channels should be restricted to a limited group of users

## Licensing Considerations

To manage who creates groups, an Azure AD Premium license is required

[Manage who can create Microsoft 365 Groups | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide#licensing-requirements)

This license can be purchased standalone or as part of the following bundles:

* EMS + E3/E5
* Microsoft 365 Business Premium
* Microsoft 365 E3
* Microsoft 365 E5

## Set Up Instructions

Resources:

To restrict who can create Teams channels (groups) follow the steps listed [here](https://learn.microsoft.com/en-us/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups)

## End-User Impact

{% hint style="info" %}
Level: <mark style="color:yellow;">Medium</mark>
{% endhint %}

It is very important that you properly plan and communicate any changes here before rolling them out. The goal is not to inhibit productivity and force users to go to outside channels to collaborate, causing shadow IT. It is imperative that you make the request for creating a new Teams channel as seamless as possible. Restricting the creation of Teams channels also restricts who can create Groups. The setting is all or nothing in this regard.

{% hint style="info" %}
Tips

None Currently
{% endhint %}

## PowerShell Scripts

[Manage who can create Microsoft 365 Groups | Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide#step-2-run-powershell-commands)

## Videos

{% embed url="https://www.youtube.com/watch?v=gCyMCy1ZKFw" %}
