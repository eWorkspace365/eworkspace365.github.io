[[_TOC_]]

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
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA03-BLOCK-GeoLocation** |  
| What does this do? | <div align="left">Blocking specific geographic locations. |  
| What is the end-user impact? | <div align="left"> Users are unable to connect from specific countries.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/> Condition: **Location** = Blocked-Countries (Exclude All trusted networks and locations) <br/> Condition: **Client Apps** = Browser; Mobile apps and dekstop clients <br/> Grant: **Block Access** |

## BL-CA04-BLOCK-ServiceAccounts
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA04-BLOCK-ServiceAccounts** |  
| What does this do? | <div align="left">Blocking service accounts. |  
| What is the end-user impact? | <div align="left"> Service accounts are unable to connect except from trusted locations.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **Group** = bl-entraid-sg-ca-service-accounts<br/>Target Resources: **All Cloud Apps**<br/> Condition: **Location** = Any network or location (Exclude named location: Service-Accounts<br/> Grant: **Block Access** |

## BL-CA05-BLOCK-HighRiskUsers
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA05-BLOCK-HighRiskUsers** |  
| What does this do? | <div align="left">Blocking high risk users. |  
| What is the end-user impact? | <div align="left"> Users marked as high risk are unable to connect.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/>Condition: **User risk** = High<br/> Grant: **Block Access** |

## BL-CA06-BLOCK-HighRiskSignins
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA06-BLOCK-HighRiskSignins** |  
| What does this do? | <div align="left">Blocking high risk signins. |  
| What is the end-user impact? | <div align="left"> Users marked as risky sign-in are unable to connect.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/>Condition: **Sign-in risk** = High<br/> Grant: **Block Access** |

## BL-CA07-BLOCK-InsiderRisk
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA07-BLOCK-InsiderRisk** |  
| What does this do? | <div align="left">Blocking users marked as insider risks. |  
| What is the end-user impact? | <div align="left"> Users marked as insider risk unable to connect from specific devices.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/> Condition: **Insider risk (Preview)** = Elevated <br/> Grant: **Block Access** |

## BL-CA08-GRANT-MediumRiskSignIns
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA08-GRANT-MediumRiskSignIns** |  
| What does this do? | <div align="left">Force MFA and password change for medium risk signins. |  
| What is the end-user impact? | <div align="left"> Users marked as risky sign-in are unable to connect.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/>Condition: **Sign-in risk** = Medium<br/> Grant: **Grant Access**; Require MFA and Require password change |

## BL-CA09-GRANT-MediumRiskUsers
| Name | <div align="left"> Configuration | 
|-----------|:-----------:|
| Name of this Policy? | <div align="left">**BL-CA09-GRANT-MediumRiskUsers** |  
| What does this do? | <div align="left">Force MFA and password change for medium risk users. |  
| What is the end-user impact? | <div align="left"> Users marked as medium risky  are unable to connect.
| What is are the settings?<br/><br/><br/> | <div align="left"> Users: **All Users** (Exclude bl-entraid-sg-ca-exlude-breakglass-accounts)<br/>Target Resources: **All Cloud Apps**<br/>Condition: **User risk** = Medium<br/> Grant: **Grant Access**; Require MFA and Require password change |