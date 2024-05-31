[Menu Item 1]()

  * # SubMenu Heading 1
  * [Prerequisites](subitem1.md)
  * [Baseline Configuration](#bl-ca01-block-legacyauthentication)
  - - - -
  * # SubMenu Heading 2
  * [SubMenu Item 3](subitem3.md)
  - - - -
  * # SubMenu Heading 3
  * [SubMenu Item 3](subitem3.md)

[Menu Item 2](item2.md)
- - - -
[Menu Item 3](item3.md)


# Prerequisites
# Baseline Configuration

[conditional-access-policy-design-baseline-version-14.xlsx](/.attachments/conditional-access-policy-design-baseline-version-14-2925dbcb-1b72-4d32-b13a-2358df5aadc8.xlsx)

## BL-CA01-BLOCK-LegacyAuthentication
> More information about this setting, please go to:<br/> https://learn.microsoft.com/en-us/entra/identity/conditional-access/block-legacy-authentication

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA01-BLOCK-LegacyAuthentication** |  
| What does this do? | Blocking legacy authentication. |  
| What is the end-user impact? | Users are unable to use the following protocols: <br/><br/> - Authenticated SMTP - Used to send authenticated email messages. <br/>- Exchange ActiveSync (EAS) - Used to connect and sync mailbox. <br/> - POP3 - Used by POP email clients. <br/> - Other clients - Other protocols identified to use legacy authentication.
| What is are the settings? | Create a policy with the following parameters:|
| **Users** | Under **Include**, select **All users** |
|**Target Resources** | Under Include, select **All cloud apps** |
| **Condition** | Under **Client apps**, select **Exchange ActiveSync clients** and **Other clients** | 
| **Grant** |  Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA02-BLOCK-DevicePlatforms
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-policy-unknown-unsupported-device

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA02-BLOCK-DevicePlatforms** |  
| What does this do? | Blocking specific device platforms. |  
| What is the end-user impact? | Users are unable to connect from specific device platforms.
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude** select group **bl-entraid-sg-ca-exlude-breakglass-accounts**) |
| **Target Resources** | Under Include, select **All cloud apps** |
| **Condition** | Under **Device platforms**, select **Windows Phone** | 
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA03-BLOCK-GeoLocation
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-location

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA03-BLOCK-GeoLocation** |  
| What does this do? | Blocking specific geographic locations |  
| What is the end-user impact? | Users are unable to connect from specific countries
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group > **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps**
| **Condition** | Under **Location** > **Include**, select location  **Blocked-Countries**<br/>Under **Location** > **Exclude**, select > **All trusted networks and locations**
| | Under **Client apps** select **Browser** and **Mobile apps and dekstop clients** |
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA04-BLOCK-ServiceAccounts
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-block-access

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA04-BLOCK-ServiceAccounts** |  
| What does this do? | Blocking service accounts |  
| What is the end-user impact? | Service accounts are unable to connect except from trusted locations
| What is are the settings? | Create a policy with the following parameters: | 
| **Users** | Under **Include**, select group > **bl-entraid-sg-ca-service-accounts** |
| **Target Resources** |  Under **Include**, select **All cloud apps** |
| **Condition** | Under **Location** > **Include**, select **Any network or location**<br/> Under **Location** > **Include**, select named location > **Service-Accounts**
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA05-BLOCK-HighRiskUsers
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA05-BLOCK-HighRiskUsers** |  
| What does this do? | Blocking high risk users |  
| What is the end-user impact? | Users marked as high risk are unable to connect
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group > **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** |  Under **Include**, select **All cloud apps** |
| **Condition** | Under **User risk**, select **High** |
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA06-BLOCK-HighRiskSignins
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA06-BLOCK-HighRiskSignins** |  
| What does this do? | Blocking high risk signins |  
| What is the end-user impact? | Users marked as risky sign-in are unable to connect
| What is are the settings? | Create a policy with the following parameters: |  | **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** |  Under **Include**, select **All cloud apps** |
| **Condition** | Under **Sign-in risk**, select **High** | 
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA07-BLOCK-InsiderRisk
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/how-to-policy-insider-risk

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA07-BLOCK-InsiderRisk** |  
| What does this do? | Blocking users marked as insider risks. |  
| What is the end-user impact? | Users marked as insider risk unable to connect from specific devices.
| What is are the settings? | Create a policy with the following parameters: | 
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Condition** | Under **Insider risk (Preview)**, select **Elevated** |
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

<br/>

## BL-CA08-GRANT-MediumRiskSignIns
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA08-GRANT-MediumRiskSignIns** |  
| What does this do? | Force MFA and password change for medium risk signins. |  
| What is the end-user impact? | Users marked as risky sign-in are unable to connect.
| What is are the settings? | Create a policy with the following parameters: | 
| **Users** |  Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Condition** | Under **Sign-in risk**, select **Medium** |
| **Grant** | Select **Grant Access** and select **Require MFA** and **Require password change** |

<br/>

## BL-CA09-GRANT-MediumRiskUsers
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA09-GRANT-MediumRiskUsers** |  
| What does this do? | Force MFA and password change for medium risk users. |  
| What is the end-user impact? | Users marked as medium risky  are unable to connect.
| What is are the settings? | Create a policy with the following parameters: |
| **Users** |  Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Condition** | Under **User risk**, select **Medium** |
| **Grant** | Select **Grant Access** and select **Require MFA** and **Require password change** |

<br/>

## BL-CA10-GRANT-Administrators
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-admin-mfa

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA10-GRANT-Administrators** |  
| What does this do? | Force MFA for administrative roles and users. |  
| What is the end-user impact? | Users with administrator roles will be forced to configure or require MFA authentication.
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **Users and groups** and select all **Administrator roles**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Grant** | Select **Grant Access** and select **Require MFA** with Operator = **OR** |
| **Session** | Select **Sign-in frequency** and set to **9 hours**<br/>Select **Persistant browser session** and select **Always persistant** |

<br/>

## BL-CA11-GRANT-Members
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-all-users-mfa

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA11-GRANT-Members** |  
| What does this do? | Force MFA for all users. |  
| What is the end-user impact? | All users will be forced to configure or require MFA authentication.
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Grant** | Select **Grant Access** and select **Require MFA** with Operator = **OR** |

<br/>

## BL-CA12-GRANT-Guests
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-policy-guest-mfa

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA12-GRANT-Guests** |  
| What does this do? | Force MFA for all guests. |  
| What is the end-user impact? | All guests will be forced to configure or require MFA authentication.
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **Users and groups** and select **Guest or external users** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Grant** | Select **Grant Access** and select **Require MFA** with Operator = **OR** |
| **Session** | Select **Sign-in frequency** and set to **9 hours**<br/>Select **Persistant browser session** and select **Always persistant** |

<br/>

## BL-CA13-GRANT-RemoteDesktop
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-compliant-device-admin

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA13-GRANT-RemoteDesktop** |  
| What does this do? | Require a compliance device or workplace join for Remote Dekstop |  
| What is the end-user impact? | All all users need a compliant device or workplace join to connect to Remote Desktop.
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users** |
| **Target Resources** | Under **Include**, select the following services:<br/><br/>[x] **Azure Windows VM Sign-In**<br/>[x] **Microsoft Remote Desktop** <br/>[x] **Windows 365** <br/>[x] **Windows Cloud Login** <br/>[x] **Windows Virtual Desktop** <br/>[x] **Windows Virtual Desktop Client**|
| **Condition** |  Under **Client apps** select **Browser** and **Mobile apps and dekstop clients** |
| | Under **Filter for devices**, select **Exclude filtered devices from policy** and enter syntax: `device.trustType -eq "Workplace"`
| **Grant** | Select **Grant Access** and select **Require device to be marked as compliant** and **Require Microsoft Entra hybrid joined device** with Operator = **OR** |
| **Session** | Select **Sign-in frequency** and set to **1 hour** |

<br/>

## BL-CA14-GRANT-ManagedDevices
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-compliant-device

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA14-GRANT-ManagedDevices** |  
| What does this do? | Require a compliance device or workplace join for all services |  
| What is the end-user impact? | All all users need a compliant device or workplace join to use Microsoft 365 services
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps**<br/>Under **Exclude**, select the following services:<br/><br/>[x] **Azure Windows VM Sign-In**<br/>[x] **Microsoft Remote Desktop** <br/>[x] **Windows 365** <br/>[x] **Windows Cloud Login** <br/>[x] **Windows Virtual Desktop** <br/>[x] **Windows Virtual Desktop Client**|
| **Condition** |  Under **Client apps** select **Mobile apps and dekstop clients** |
| **Grant** | Select **Grant Access** and select **Require device to be marked as compliant** and **Require Microsoft Entra hybrid joined device** with Operator = **AND** |

<br/>

## BL-CA15-GRANT-ApprovedApps
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-policy-approved-app-or-app-protection

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA15-GRANT-ApprovedApps** |  
| What does this do? | Require an approved app |  
| What is the end-user impact? | All all users need an approved app to use Microsoft 365 services
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Condition** |  Under **Device platforms** select the following platforms: <br/><br/>[x] **Android**<br/>[x] **iOS** |
| **Grant** | Select **Grant Access** and select **Require approved client app**  with Operator = **OR** |

<br/>

## BL-CA16-GRANT-RegisterSecurityInfo
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-registration

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA16-GRANT-RegisterSecurityInfo** |  
| What does this do? | Require to check security information |  
| What is the end-user impact? | Administrators need to check security information |
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select **Guest or external users** and select **All** for External organizations and select directory roles **Global Administrators** |
| **Target Resources** | Under **User actions**, select **Register security information** |
| **Condition** |  Under **Locations** > **Include**, select **Any network location**<br/> Under **Location** > **Exclude**, select **All trusted networks and locations** |
| **Grant** | Select **Grant Access** and select **Require MFA**  with Operator = **OR** |

<br/>

## BL-CA17-GRANT-TermsofUse
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/require-tou

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA17-GRANT-TermsofUse** |  
| What does this do? | Require to accept terms of use |  
| What is the end-user impact? | All user need to accept the terms of use |
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps** |
| **Grant** | Select **Grant Access** and select the company's **Terms of Use**  with Operator = **OR** |

<br/>

## BL-CA18-SESSION-AppEnforcedRestrictions
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-policy-app-enforced-restriction

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA18-SESSION-AppEnforcedRestrictions** |  
| What does this do? | Block or limit access to SharePoint, OneDrive, and Exchange content from unmanaged devices  |  
| What is the end-user impact? | Users are not allowed to download, print or sync on un-managed devices |
| What is are the settings? | Create a policy with the following parameters: |
| **Users** | Under **Include**, select **All users**<br/>Under **Exclude**, select group **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **Selected apps**:<br/><br/>[x] **Office 365 SharePoint Online**  |
| **Condition** | Under **Client apps** select **Browser** |
| **Grant** | Select **Grant Access** and select **Use app enforced restrictions**  with Operator = **OR** |
