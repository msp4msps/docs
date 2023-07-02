# Automating Microsoft 365 Documentation in Syncro

Documenting customer Microsoft 365 environments can be extremely tedious and time consuming. Keeping that information up to date is also a heavy task to manage. I wanted to create some scripts that would automate and update documents in Syncro that are tied to your customer environments. For this reason I create a some scripts that perform the following:

* **Microsoft License Information** => Displays all current licensed and unlicensed users as well as showing what licenses are available vs. consumed
* **Microsoft MFA Status** => Displays MFA status, Conditional Access Policies, and DUO MFA custom controls
* **Microsoft Exchange Information** => Displays mailbox usage in GB, last login time, mailflow rules, DKIM Config, and ATP policies
* **Microsoft Intune Information** => Displays enrolled devices, compliance status, OS version, Autopilot info, encryption, and Assigned Apps
* Microsoft Contact Creation => Creates a contact on the customer record in Syncro for Active 365 Users

All documentation is listed for the customer and contacts are automatically added or updated to the customer record.

![](https://tminus365.com/wp-content/uploads/2021/04/pic8-1.png)

All of my scripts can be found at the following repository

![](https://tminus365.com/wp-content/uploads/2021/04/Syncro-Logo-768x205.png)

### Microsoft License Report

The license report displays all active and consumed licensing as well as all licensed and unlicensed users

![](https://tminus365.com/wp-content/uploads/2021/04/pic6-1.png)

![](https://tminus365.com/wp-content/uploads/2021/04/pic7-1.png)

### Microsoft MFA Status

This report shows you all users MFA status. Since Microsoft has evolved their MFA registration over time there are now 3 different ways in which a user could have MFA enforced.

* Legacy MFA Portal (where you see Enabled, Enforced, Disabled)
* Conditional Access Policies
* Security Defaults

For this reason I include two columns that shows if a user has registered with one of these methods (I am able to see Security Defaults and Conditional Access Registration in a combined output). Here I also show the names of all Conditional Access Policies and also an additional filed that shows if you have DUO listed as a custom control in any conditional access policy

![](https://tminus365.com/wp-content/uploads/2021/04/pic9-1.png)

![](https://tminus365.com/wp-content/uploads/2021/04/pic10-1.png)

### Microsoft Exchange Report

For the exchange report, I show mailboxes, active consumption in GB (in a descending order), last login time, mailflow rules, DKIM Configuration, and ATP Settings/Policies

![](https://tminus365.com/wp-content/uploads/2021/04/pic11-1.png)

![](https://tminus365.com/wp-content/uploads/2021/04/pic12-1.png)

### Microsoft Intune Report

The Intune report contains a summary of device compliance, devices, and all apps that are in an assigned state

![](https://tminus365.com/wp-content/uploads/2021/04/pic13-2.png)

### Microsoft Contact Creation

Microsoft 365 Users are created as contacts for a customer if they do not already exist. If the user is not longer in 365, then a note is added to an existing contact to say that they are no longer active. (Wish there was a flag or something for this in Syncro as it wasn’t the best way to show removal of users)

![](https://tminus365.com/wp-content/uploads/2021/04/pic14-1.png)

### Prerequisites

You will need to garner tokens and GUIDs from both the Secure Application Model and Syncro. The secure application model allows for a headless connection into all of your customer environments. The script to run that can be found from Kelvin over at CyberDrain. [Click here to go to that page in Github.](https://github.com/KelvinTegelaar/SecureAppModel/blob/master/Create-SecureAppModel.ps1) In Syncro you will need to create a new API Key that has permissions to customers and documentation to perform the necessary read and write actions. [Click Here for Syncro’s Documentation on generating a new API key](https://help.syncromsp.com/hc/en-us/articles/360048794414-API-Tokens). The only other variable you will be prompted for is your Syncro subdomain. This is simply just the prefix of the URL you go to when signing in. Ex:

![](https://tminus365.com/wp-content/uploads/2021/04/pic15-1.png)
