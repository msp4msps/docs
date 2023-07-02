# Automating Intune Device Documentation in IT Glue

As we continue to shift the management of devices to Intune, I wanted an easy way to see all of the devices across all customers.  I wanted to include metadata at a multi-tenant level such as device compliance and autopilot enrollment. I created a script that creates a new flexible asset in IT Glue and populates it with all enrolled devices per company. The script creates new devices or updates existing devices. You will be able to document the following:

* **Device Name**
* **Ownership (Corporate or Personal)**
* **OS**
* **OS Version**
* **Compliance State**
* **User**
* **Autopilot Enrolled**
* **Encrypted**
* **Serial Number**
* **Configurations(if existing)**

![](https://tminus365.com/wp-content/uploads/2021/05/pic5.png)

![](https://tminus365.com/wp-content/uploads/2021/05/pic7.png)

### Prerequisites

You will need to garner tokens and GUIDs from both the Secure Application Model and Syncro. The secure application model allows for a headless connection into all of your customer environments. The script to run that can be found from Kelvin over at CyberDrain. [Click here to go to that page in Github.](https://github.com/KelvinTegelaar/SecureAppModel/blob/master/Create-SecureAppModel.ps1)

In IT Glue you will need to create a new API Key. [Click Here for IT Glue’s Documentation on generating a new API key](https://support.itglue.com/hc/en-us/articles/360004938078-Getting-started-with-the-IT-Glue-API).

In Microsoft, you will need to make sure you add the following permissions from the ap that was created with the Secure Application model if they are not already there:

* DeviceManagementConfiguration.Read.All
* DeviceManagementManagedDevices.Read.All

Reference [the following documentation](https://support.itglue.com/hc/en-us/articles/360004938078-Getting-started-with-the-IT-Glue-API) for steps on adding permission to your app registration.

### The Script

```
Param
(

[cmdletbinding()]
    [Parameter(Mandatory= $true, HelpMessage="Enter your ApplicationId from the Secure Application Model https://github.com/KelvinTegelaar/SecureAppModel/blob/master/Create-SecureAppModel.ps1")]
    [string]$ApplicationId,
    [Parameter(Mandatory= $true, HelpMessage="Enter your ApplicationSecret from the Secure Application Model")]
    [string]$ApplicationSecret,
    [Parameter(Mandatory= $true, HelpMessage="Enter your Partner Tenantid")]
    [string]$tenantID,
    [Parameter(Mandatory= $true, HelpMessage="Enter your refreshToken from the Secure Application Model")]
    [string]$refreshToken,
    [Parameter(Mandatory= $true, HelpMessage="Enter your IT Glue API Key")]
    [string]$APIKey,
    [Parameter(Mandatory= $true, HelpMessage="Enter your IT Glue URL, ex: https://api.itglue.com")]
    [string]$APIEndpoint

)


###Additional API Permissions Need for App in Azure AD ####

####DeviceManagementConfiguration.Read.All
####DeviceManagementManagedDevices.Read.All


###MICROSOFT SECRETS#####

$ApplicationId = $ApplicationId
$ApplicationSecret = $ApplicationSecret
$tenantID = $tenantID
$refreshToken = $refreshToken
$secPas = $ApplicationSecret| ConvertTo-SecureString -AsPlainText -Force
$credential = New-Object System.Management.Automation.PSCredential($ApplicationId, $secPas)

########################## IT-Glue Information ############################
$APIKey = $APIKey
$APIEndpoint = $APIEndpoint
$FlexAssetName = "Intune Devices"
$Description = "Documentation for all devices enrolled into Intune"

write-host "Getting IT-Glue module" -ForegroundColor Green
 
If (Get-Module -ListAvailable -Name "ITGlueAPI") { 
    Import-module ITGlueAPI 
}
Else { 
    Install-Module ITGlueAPI -Force
    Import-Module ITGlueAPI
}
#Settings IT-Glue logon information
Add-ITGlueBaseURI -base_uri $APIEndpoint
Add-ITGlueAPIKey $APIKEy

write-host "Checking if Flexible Asset exists in IT-Glue." -foregroundColor green
$FilterID = (Get-ITGlueFlexibleAssetTypes -filter_name $FlexAssetName).data
if (!$FilterID) { 
    write-host "Does not exist, creating new." -foregroundColor green
    $NewFlexAssetData = 
    @{
        type          = 'flexible-asset-types'
        attributes    = @{
            name        = $FlexAssetName
            icon        = 'laptop'
            description = $description
        }
        relationships = @{
            "flexible-asset-fields" = @{
                data = @(
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order           = 1
                            name            = "Device Name"
                            kind            = "Text"
                            required        = $true
                            "show-in-list"  = $true
                            "use-for-title" = $true
                        }
                    },

                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 2
                            name           = "Ownership"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 3
                            name           = "OS"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 4
                            name           = "OS Version"
                            kind           = "Text"
                            required       = $false
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 5
                            name           = "Compliance State"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 6
                            name           = "User"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 7
                            name           = "Autopilot Enrolled"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 8
                            name           = "Encrypted"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 9
                            name           = "Serial Number"
                            kind           = "Text"
                            required       = $true
                            "show-in-list" = $true
                        }
                    }
                    @{
                        type       = "flexible_asset_fields"
                        attributes = @{
                            order          = 10
                            name           = "Configurations"
                            'tag-type'     = "Configurations"
                            kind           = "Tag"
                            required       = $false
                            "show-in-list" = $true
                        }
                    }
                     
                )
            }
        }
    }
    New-ITGlueFlexibleAssetTypes -Data $NewFlexAssetData
    $FilterID = (Get-ITGlueFlexibleAssetTypes -filter_name $FlexAssetName).data
}


#Grab all IT-Glue contacts to match the domain name.
write-host "Getting IT-Glue contact list" -foregroundColor green
$i = 1
$AllITGlueContacts = do {
    $Contacts = (Get-ITGlueContacts -page_size 1000 -page_number $i).data.attributes
    $i++
    $Contacts
    Write-Host "Retrieved $($Contacts.count) Contacts" -ForegroundColor Yellow
}while ($Contacts.count % 1000 -eq 0 -and $Contacts.count -ne 0) 


$i=1
$AllITGlueConfigurations = do {
    $Configs = (Get-ITGlueConfigurations -page_size 1000 -page_number $i).data
    $i++
    $Configs
    Write-Host "Retrieved $($Configs.count) Configurations" -ForegroundColor Yellow
}while ($Configs.count % 1000 -eq 0 -and $Configs.count -ne 0) 

$DomainList = foreach ($Contact in $AllITGlueContacts) {
    $ITGDomain = ($contact.'contact-emails'.value -split "@")[1]
    [PSCustomObject]@{
        Domain   = $ITGDomain
        OrgID    = $Contact.'organization-id'
        Combined = "$($ITGDomain)$($Contact.'organization-id')"
    }
} 


###Connect to your Own Partner Center to get a list of customers/tenantIDs #########
$aadGraphToken = New-PartnerAccessToken -ApplicationId $ApplicationId -Credential $credential -RefreshToken $refreshToken -Scopes 'https://graph.windows.net/.default' -ServicePrincipal -Tenant $tenantID
$graphToken = New-PartnerAccessToken -ApplicationId $ApplicationId -Credential $credential -RefreshToken $refreshToken -Scopes 'https://graph.microsoft.com/.default' -ServicePrincipal -Tenant $tenantID


Connect-MsolService -AdGraphAccessToken $aadGraphToken.AccessToken -MsGraphAccessToken $graphToken.AccessToken

$customers = Get-MsolPartnerContract -All
 
Write-Host "Found $($customers.Count) customers in Partner Center." -ForegroundColor DarkGreen

foreach ($customer in $customers) {
    Write-Host "Found $($customer.Name) in Partner Center" -ForegroundColor Green

    ###Get Access Token########
    $CustomerToken = New-PartnerAccessToken -ApplicationId $ApplicationId -Credential $credential -RefreshToken $refreshToken -Scopes 'https://graph.microsoft.com/.default' -Tenant $customer.TenantID
    $headers = @{ "Authorization" = "Bearer $($CustomerToken.AccessToken)" }
    $Devices = ""

    #####Get Intune information if it is available####
    try{
    $Devices = (Invoke-RestMethod -Uri 'https://graph.microsoft.com/beta/deviceManagement/managedDevices' -Headers $headers -Method Get -ContentType "application/json").value | Select-Object deviceName, ownerType, operatingSystem, osVersion, complianceState,userPrincipalName, autopilotEnrolled,isEncrypted, serialNumber
    }catch{('This tenant either does not have intune licensing or you have not added the correct permissions to the which are listed in the begining of this script')} 

    if($Devices){
       forEach($device in $Devices){
        forEach($configuration in $AllITGlueConfigurations){
            if($configuration.attributes.'serial-number' -eq $device.serialNumber){
                $configExist = $configuration
                Write-Host "Existing Configuration Found in ITGlue" -ForegroundColor Cyan
            } else {
                $configExist = ""
            }
        }
        $FlexAssetBody =
        @{
        type       = 'flexible-assets'
        attributes = @{
            traits = @{
             'device-name'              = $device.deviceName
             'ownership'                = $device.ownertype
             'os'                       = $device.operatingSystem
             'os-version'               = $device.osVersion
             'compliance-state'         = $device.complianceState
             'user'                     = $device.userPrincipalName
             'autopilot-enrolled'       = $device.autopilotEnrolled | Out-String
             'encrypted'                = $device.isEncrypted | Out-String
             'serial-number'            = $device.serialNumber
             'configurations'           = $configExist.id
            }
        }
    }
    Write-Host "Finding $($customer.name) in IT-Glue" -ForegroundColor Green
    $CustomerDomains = Get-MsolDomain -TenantId $Customer.TenantId
    $orgid = foreach ($customerDomain in $customerdomains) {
        ($domainList | Where-Object { $_.domain -eq $customerDomain.name }).'OrgID'
    }

    $orgID = $orgid | Select-Object -Unique
    if(!$orgID){
       Write-Host "$($customer.name) does not exist in IT-Glue" -ForegroundColor Red
    }
    if($orgID){
    $ExistingFlexAsset = (Get-ITGlueFlexibleAssets -filter_flexible_asset_type_id $($filterID.id) -filter_organization_id $orgID).data | Where-Object { $_.attributes.traits.'serial-number' -eq $device.serialNumber}
        #If the Asset does not exist, we edit the body to be in the form of a new asset, if not, we just update.
        if (!$ExistingFlexAsset) {
            $FlexAssetBody.attributes.add('organization-id', $orgID)
            $FlexAssetBody.attributes.add('flexible-asset-type-id', $($filterID.ID))
            write-host "Creating Intune Device $($device.deviceName) for $($customer.name) into IT-Glue organisation $org" -ForegroundColor Green
            New-ITGlueFlexibleAssets -data $FlexAssetBody
        }
        else {
            write-host "Updating Intune Device $($device.deviceName) for $($customer.name) into IT-Glue organisation $org"  -ForegroundColor Yellow
            $ExistingFlexAsset = $ExistingFlexAsset | select-object -last 1
            Set-ITGlueFlexibleAssets -id $ExistingFlexAsset.id -data $FlexAssetBody
        }
    }
    }}}
```

### Final Thoughts

The script is looking for Serial Numbers to soft match an Intune enrolled device to an existing configuration and add them as a tag to the asset. I did have the thought of creating Intune devices as new configurations if they didn’t perform that soft match of the serial number but would want some feedback on that! Additionally, if you think there would be more metadata you would like to see that is part of the device, please comment that below.&#x20;
