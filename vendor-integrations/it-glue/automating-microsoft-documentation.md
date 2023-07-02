# Automating Microsoft Documentation

M365 DOCUMENTATION

[![github-follow](https://camo.githubusercontent.com/ba59463c3f24508a1d1bb823d741c25cf6b27ba86cb54d5a775ca6cdb1232ed3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f666f6c6c6f776572732f6d7370346d7370733f6c6162656c3d466f6c6c6f77266c6f676f436f6c6f723d707572706c65267374796c653d736f6369616c)](https://github.com/msp4msps) [![project-languages-used](https://camo.githubusercontent.com/83eeec810299fe365b6113bbc141c3822ef7746a3cc90193c2a08c933324c0f8/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c616e6775616765732f636f756e742f6d7370346d7370732f6d3336355f646f63756d656e746174696f6e3f636f6c6f723d696d706f7274616e74)](https://github.com/msp4msps/m365\_documentation) [![project-top-language](https://camo.githubusercontent.com/11d1c462d6e239f58cc94cc744d3f333f37b3df16b0c0a3333b6fdb3921e52f1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c616e6775616765732f746f702f6d7370346d7370732f6d3336355f646f63756d656e746174696f6e3f636f6c6f723d626c756576696f6c6574)](https://github.com/msp4msps/m365\_documentation) [![license](https://camo.githubusercontent.com/28044ecf31ba56f2684bd081fb809249487c05239a228658182c516040b1088f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c6963656e73652d4d49542d627269676874677265656e2e737667)](https://choosealicense.com/licenses/mit/)

### Table of Contents

* [Project Links](broken-reference)
* [Screenshots](broken-reference)
* [Project Description](broken-reference)
* [User Story](broken-reference)
* [Technologies](broken-reference)
* [Installation](broken-reference)
* [Usage](broken-reference)
* [Credits and Reference](broken-reference)
* [Tests](broken-reference)
* [Contributing](broken-reference)
* [Questions](broken-reference)
* [License](broken-reference)

### Project Links

[https://github.com/msp4msps/m365\_documentation](https://github.com/msp4msps/m365\_documentation)\


### Screenshots

<figure><img src="../../.gitbook/assets/m365docs.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/m365docs2.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/m365docs3.png" alt=""><figcaption></figcaption></figure>

### Project Description

The following project was created to house scripts for documenting M365 tenants for customers that you manage. Today the documentation consist of CSV files and flexible assets in IT Glue. These scripts leverage the Secure Application model to create a secure connection to all customers under management in Partner Center.

### Information Collected

Microsoft Users

* DisplayName
* FirstName
* UPN
* Role
* JobTitle
* LicensesAssigned
* LastSignIn
* createdDateTime
* accountEnabled
* AccountType
* LastPasswordChange
* PasswordExpiration
* MFARegistered
* ExchangeLastActive
* MailboxStorageUsedGB
* MailboxItemCount
* HasArchive
* AuthMethod:Phone
* AuthMethod:Email
* OneDriveLastActive
* OneDriveStorageUsed
* OneDriveFileCount
* OneDriveViewed/EditedFileCount
* OneDriveSyncedFileCount
* OneDriveSharedInternalFileCount
* OneDriveSharedExternalFileCount
* SharePointLastActive
* SharePointViewed/EditedFileCount
* SharePointSyncedFileCount
* SharePointSharedInternalFileCount
* SharePointSharedExternalFileCount
* SharePointVisitedPageCount
* TeamsLastActive
* TeamsChatCount
* TeamsCallCount
* TeamsMeetingCount

MS Groups

* GroupName
* Email
* Group Type
* Membership Type
* Creation Date
* Source
* Security Enabled
* Visibility
* HideFromGal
* Teams Connected
* Owners
* Members

MS Devices

* DeviceName
* Enabled
* OS
* Version
* JoinType
* UserName
* ManagementType
* Compliance
* DeviceOwnership
* RegisteredDate
* LastActivityDate
* AutopilotEnrolled
* isEncrypted
* SerialNumber

SharePoint Sites

* Site Name
* Site URL
* Last Activity Date
* Site File Count
* Site Storage Used (GB)
* Storage Allocated (GB)
* Microsoft Group Connected

Exchange Settings

* Legacy Auth Settings
* Mail Transport Rules
* OWA Policies
* Accepted Domains
* Mobile Device Policies
* Retention Policies
* Retention Policy Tags
* Journal Rules
* Antiphish Policies
* Outbound Spam Policies
* AntiSpam Policies
* Malware Policies
* Safe Attachment Policies
* Safe Link Policies
* DKIM settings

Azure AD Settings

* Conditional Acces Policies
* Legacy Auth Sign Ins
* Named Locations
* Self-Service Password Reset Settings
* Can Users Register Applications
* Can Users Consent for Applications

Intune Settings

* Windows Compliance Policies
* macOS Compliance Policies
* iOS Compliance Policies
* Android Compliance Policies
* Windows Information Protection Policies
* iOS App Protection Policies
* Android App Protection Policies
* Configuration Profiles
* Applications
* App Configuration Profiles

### User Story

As an MSP, I would like granular documentation on users, groups, and organization settings that can help me be more proactive in managing customer environments.

### Installation

1. Leverage the Create\_Auth.ps1 file if you have not already created an app registration to garner tokens for authenticating to customer environments.
2. Leverage the Remove\_AnonymidedReports.ps1 file to ensure all customers have reports that are not anonymized. You could do this at a per customer basis as well.
3. Fork the repo to modify the scripts or leverage the scripts to start documenting customer environments.

### Usage

I would start by running single tenant scripts to see if that creates the information you are looking for and modifying accordingly. This is especially important in IT Glue where you may want to modify the format of the flexible asset.

### Credits and Reference

Kelvin Tegelaar for his work on the Secure Application Model that makes this possible. Gavin Stone for his script on garnering info on Conditional Access policies which I reused here. I will be looking to add this information into CIPP at a later date.

### Tests

Run against a single customer tenant

### Contributing

Open a pull request with any issues or feature enhancements.

