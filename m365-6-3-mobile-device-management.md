[Microsoft 365](index.md#microsoft365) > [6. Microsoft Intune](m365-6-0-microsoft-intune.md) > **Mobile Device Management (MDM)**

### In this article
>    * [EndPoint Privileged Management](#azure)
>    * [Configuration Profiles](azure-1-0-entraid.md)
>    * [Compliance Policies](azure-1-0-entraid.md)

https://learn.microsoft.com/en-us/windows/security/operating-system-security/device-management/windows-security-configuration-framework/security-compliance-toolkit-10

https://www.microsoft.com/en-us/download/details.aspx?id=55319


## Configuration Profiles

### EndPoint Privileged Management

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Endpoint security** > **Endpoint Privilege Management** > select the **Policies** tab > and then select **Create Policy**.
   Set the *Platform* to **Windows**, *Profile* to **Windows elevation settings policy**, and then select **Create**.

2. On **Basics**, enter the following properties:

   - **Name**: bl-win-cfg-privilege-mgmt
  
3. On **Assignments**, include the following group:

   - **Group**: All Users
  
4. On **Configuration settings**, configure the following settings:

![image](https://github.com/user-attachments/assets/e65829b8-b41f-4f23-87aa-39ef8f0d2db1)

> [!TIP]
> Endpoint Privilege Management is available as an Intune add-on which requires an additional license to use, and supports Windows 10 and Windows 11 devices. For more information, see [Endpoint Privilege Management](https://learn.microsoft.com/en-us/mem/intune/protect/epm-overview).

### Settings Catalog

1. Download the JSON files from the [IntuneBaseline](https://github.com/eWorkspace365/m365-landingzone/tree/main/6-microsoft-intune/mdm/settings-catalog) repository.
2. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to Devices > Windows > Configuration and select **Import Policy**.





For all the **catalog settings** use the json-file to import all the baseline configuration profiles:

[Download Configuration Profiles](https://github.com/eWorkspace365/m365-landingzone/tree/main/6-microsoft-intune/mdm/settings-catalog)

![image](https://github.com/user-attachments/assets/2909a342-7ade-4132-8136-8b7a62c0734a)

For **device restrictions** configure the setting manually.
For more information see: https://learn.microsoft.com/nl-nl/mem/intune/fundamentals/protection-configuration-levels

**Windows**

To configure Winget AutoUpdate in Intune, import and create custom administrative templates. These polcicies can be downloaded for Github: https://github.com/Romanitho/Winget-AutoUpdate

![image](https://github.com/user-attachments/assets/c3492ef6-dff3-419b-8744-67364f489b5f)

![image](https://github.com/user-attachments/assets/ca940e04-dd68-4881-8057-6c4cdd7a39a9)



Go Home > Devices > Windows > Configuration Profiles: 

Create a new profile with type: Device restrictions   
Name of the profile: bl-win-cfg-restrictions   
Set all the restrictions according Windows security level 2:

**iOS** 

Go Home > Devices > iOS/iPadOS > Configuration Profiles: 

Create a new profile with type: Device restrictions   
Name of the profile: bl-ios-cfg-restrictions   
Set all the restrictions according iOS security level 2:  





| Section | Setting | Value |
| --- | --- | --- |
| App Store, Doc Viewing, Gaming | Treat AirDrop as an unmanaged destination | Yes |
| App Store, Doc Viewing, Gaming | Block viewing corporate documents in unmanaged apps | Yes |
| App Store, Doc Viewing, Gaming | Block viewing non-corporate documents in corporate apps | Not configured |
| App Store, Doc Viewing, Gaming | Allow managed apps to write contacts to unmanaged contacts accounts | Yes |
| App Store, Doc Viewing, Gaming | Allow copy/paste to be affected by managed open-in | Not configured |
| Built-in Apps | Block Siri while device is locked | Yes |
| Built-in Apps | Require Safari fraud warnings | Yes |
| Built-in Apps | Block Siri for dictation | Yes |
| Built-in Apps | Block Siri for translation | Yes |
| Cloud and Storage | Force encrypted backup | Yes |
| Cloud and Storage | Block managed apps from storing data in iCloud | Yes |
| Cloud Storage | Block backup of enterprise books | Yes |
| Cloud Storage | Block notes and highlights sync for enterprise books | Yes |
| Connected Devices | Force Apple Watch wrist detection | Yes |
| General | Block untrusted TLS certificates | Yes |
| General | Block trusting new enterprise app authors | Yes |
| General | Block sending diagnostic and usage data to Apple | Yes |
| Locked Screen Experience | Block Notification Center access in lock screen | Yes |
| Locked Screen Experience | Block Today view in lock screen | Yes |
| Password | Require a password | Yes |
| Password | Block simple passwords | Yes |
| Password | Required password type | Numeric |
| Password | Minimum password length | 6 |
| Password | Number of sign-in failures before wiping the device | 10 |
| Password | Maximum minutes after screen lock before password is required | 5 |
| Password | Maximum minutes of inactivity until screen locks | 5 |

**Android** 

Go Home > Devices > Android > Configuration Profiles: 

Create a new profile with type: Device restrictions   
Name of the profile: bl-and-cfg-restrictions    
Set all the restrictions according Android security level 2:  

| Section | Setting | Value |
| --- | --- | --- |
| Device password | Minimum password length | 6 |
| Device password | Maximum minutes of inactivity until screen locks | 5 |
| Device password | Number of sign-in failures before wiping device | 10 |
| Device password | Password expiration (days) | Not configured |
| Device password | Required password type | Numeric complex |
| Device password | Prevent reuse of previous passwords | Not configured |
| System Security | Threat scan on apps | Require |
| System Security | Prevent app installations from unknown sources in the personal profile | Block |
| Work profile settings | Copy and paste between work and personal profiles | Block |
| Work profile settings | Data sharing between work and personal profiles | Apps in work profile can handle sharing request from personal profile |
| Work profile settings | Work profile notifications while device locked | Not configured |
| Work profile settings | Default app permissions | Device Default |
| Work profile settings | Add and remove accounts | Block |
| Work profile settings | Contact sharing via Bluetooth | Enable |
| Work profile settings | Screen capture | Block |
| Work profile settings | Search work contacts from personal profile | Not configured |
| Work profile settings | Allow widgets from work profile apps | Enable |
| Work profile settings | Require Work Profile Password | Require |
| Work profile settings | Minimum password length | 6 |
| Work profile settings | Maximum minutes of inactivity until work profile locks | 5 |
| Work profile settings | Number of sign-in failures before wiping the work profile | 10 |
| Work profile settings | Password expiration (days) | Numeric |
| Work profile settings | Required password type | 6 |
| Work profile settings | Prevent reuse of previous passwords | 10 |


**Compliance Policies** 

Compliance policies are commonly used in combination with Conditional Access. The Company Portal App synchronizes the device state to Intune and compares it with the compliancy policy that is targeted for the device.  

To meet with the compliancy policy that has been targeted, of course we enforce these settings first in the configuration policy. It is basically checking if those settings were applied. 

https://learn.microsoft.com/en-us/mem/intune/fundamentals/deployment-plan-compliance-policies#level-2---enhanced-device-compliance-settings


If the device meets the compliance policy, then Intune marks the device as compliant and access to company resources is granted. 

| iOS |
| --- |
| iOS/iPadOS device compliance security configurations - Microsoft Intune |
| Security Level 1 |
| Security Level 2 |
| Security Level 3 |

Go Home > Devices > iOS/iPadOS > Compliance Policies: 

Create a new profile name: IOS-DEV-Compliancy-L2   
Set all the restrictions according iOS security level 2:   
   
