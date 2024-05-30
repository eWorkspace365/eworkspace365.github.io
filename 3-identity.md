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
| What is are the settings? | **Users** > All Users (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)
| | **Target Resources** > All Cloud Apps
| | **Condition** > Sign-in risk = Medium
| | **Grant** > Grant Access = Require MFA and Require password change |

<br/>
