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

| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA01-BLOCK-LegacyAuthentication** |  
| What does this do? | <div align="left">Blocking legacy authentication. |  
| What is the end-user impact? <br/><br/><br/><br/><br/><br/> | <div align="left"> Users are unable to use the following protocols: <br/><br/> - Authenticated SMTP - Used to send authenticated email messages. <br/>- Exchange ActiveSync (EAS) - Used to connect and sync mailbox. <br/> - POP3 - Used by POP email clients. <br/> - Other clients - Other protocols identified to use legacy authentication.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** <br/>Target Resources: **All Cloud Apps**<br/> Condition: **Client Apps** = Exchange ActiveSync clients; Other clients <br/> Grant: **Block Access** |

## BL-CA02-BLOCK-DevicePlatforms
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-policy-unknown-unsupported-device

| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA02-BLOCK-DevicePlatforms** |  
| What does this do? | <div align="left">Blocking specific device platforms. |  
| What is the end-user impact? | <div align="left"> Users are unable to connect from specific device platforms.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/> Condition: **Device platforms** > Windows Phone <br/> Grant: **Block Access** |

## BL-CA03-BLOCK-GeoLocation
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-location

| Name | Configuration | 
|:-----------|:-----------|
| Name of this Policy? | **BL-CA03-BLOCK-GeoLocation** |  
| What does this do? | Blocking specific geographic locations. |  
| What is the end-user impact? | Users are unable to connect from specific countries.
| What is are the settings? | Create apoliciy with the following parameters: |
| **Users** | Under **Include**, select **All users**.<br/>Under **Exclude**, select group > **bl-entraid-sg-ca-exlude-breakglass-accounts** |
| **Target Resources** | Under **Include**, select **All cloud apps**
| **Condition** | Under **Location** > **Include**, select location  **Blocked-Countries**<br/>Under **Location** > **Exclude**, select > **All trusted networks and locations**
| | Under **Client apps** select **Browser** and **Mobile apps and dekstop clients** |
| **Grant** | Select **Block Access** and select **Require one of the selected controls** |

## BL-CA04-BLOCK-ServiceAccounts
> More information about this setting, please go to:
https://learn.microsoft.com/en-us/entra/identity/conditional-access/howto-conditional-access-policy-block-access
