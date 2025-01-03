[Microsoft 365](index.md#microsoft365) > [6. Microsoft Intune](m365-6-0-microsoft-intune.md) > **Mobile Device Management (MDM)**

# Mobile Device Management (MDM)
### In this article
>    * [Device Lifecycle](#device-lifecycle)
>    * [Configuration Profiles](#configuration-profiles)
>    * [Compliance Policies](#compliance-policies)
>    * [Scripts and Remediations](#scripts-and-remediations)
<br/>

## Device Lifecycle
Device Lifecycle Management (DLM) with Microsoft Intune involves several stages:

1. **Enrollment**: Devices are registered with Intune for management.
2. **Configuration**: Policies are applied to ensure devices meet security and compliance standards.
3. **Protection**: Security measures are implemented to safeguard data and devices.
4. **Retirement**: Devices are securely wiped and decommissioned when no longer needed

![image](https://github.com/user-attachments/assets/170715ea-b572-4faa-9f41-58645191e92e)

### Windows AutoPilot 
1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Devices** > **Windows** > **Enrollment**.
2. Select **Automatic Enrollment** and set both **MDM user scope** and **(WIP) user scope** to **All**.
3. Select **Device platform restriction** and configure default setting: <br/>

![image](https://github.com/user-attachments/assets/18bf6f9d-3c4b-4579-965a-f17248da91e3)

5. Select and configure **Windows Hello for Business** and assign to **All users**: <br/>

| Setting | Value |
| :--- | :--- |
| Configure Windows Hello for Business | Enabled |
| Use a Trusted Platform Module (TPM) | Required |
| Minimum PIN length | 6 |
| Maximum PIN length | 127 |
| Lowercase letters in PIN | Not allowed |
| Uppercase letters in PIN | Not allowed |
| Special characters in PIN | Not allowed |
| PIN expiration (days) | Never |
| Remember PIN history | No |
| Allow biometric authentication | Yes |
| Use enhanced anti-spoofing, when available | Yes |
| Allow phone sign-in | Yes |
| Enable enhanced sign in security | Enabled |
| Use security keys for sign-in | Not configured |

6. Select and configure **Deployment profiles** and assign the User-Driven profile to security group **bl-sg-devices-windows-autopilot**.

![image](https://github.com/user-attachments/assets/a0998b45-c70f-4ce4-97d3-ad7da8a6c7d3)

7. Create a custom security group for the **Self-Deploying** profile and for both profiles configure the following settings:

| Setting | Value |
| :--- | :--- |
| Join to Microsoft Entra ID as | Microsoft Entra joined |
| Language (Region) | Operating system default |
| Automatically configure keyboard | Yes |
| Microsoft Software License Terms | Hide |
| Privacy settings | Hide |
| Hide change account options | Hide |
| User account type | Standard |
| Allow pre-provisioned deployment | No |
| Apply device name template | Yes |
| Enter a name | dev-win-mdm-%RAND:1% |

### Device clean-up rules
Set your Intune device cleanup rules to delete Intune MDM enrolled devices that appear inactive, stale, or unresponsive. Intune applies cleanup rules immediately and continuously so that your device records remain current.

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Devices** > **Device clean-up rules** and configure **Delete devices based on last check-in date** and set to 45 day.

![image](https://github.com/user-attachments/assets/fb5617b9-f773-4e15-ba29-5d602b4a7c02)


## Configuration Profiles

> Endpoint Privilege Management is available as an Intune add-on which requires an additional license to use, and supports Windows 10 and Windows 11 devices. For more information, see [Endpoint Privilege Management](https://learn.microsoft.com/en-us/mem/intune/protect/epm-overview).

<br/>

### Settings Catalog

1. Download the JSON files from the [IntuneBaseline](https://github.com/eWorkspace365/m365-landingzone/tree/main/6-microsoft-intune/mdm/settings-catalog) repository.
2. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to Devices > Windows > Configuration and select **Import Policy**.

3. For all the **catalog settings** use the json-file to import all the baseline configuration profiles:

![image](https://github.com/user-attachments/assets/2909a342-7ade-4132-8136-8b7a62c0734a)

<br/>

### Custom Templates
> The Microsoft [Security Configuration Toolkit](https://www.microsoft.com/en-us/download/details.aspx?id=55319) enables enterprise security administrators to effectively manage their enterprise’s Group Policy Objects (GPOs).

<br/>

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Devices** > **Configuration** and select tab **Import ADMX**. Import the templates from Github: https://github.com/Romanitho/Winget-AutoUpdate

2. Go to **Devices** > **Windows** > **Configuration** and select **Create** > **New Policy**.
3. Select platform **Windows 10 and later** and profile type **Templates** > **Imported Administrative templates**.
   
![image](https://github.com/user-attachments/assets/c3492ef6-dff3-419b-8744-67364f489b5f)

5. Configure thefowlling setting for Winget AutoUpdate:
   
![image](https://github.com/user-attachments/assets/ca940e04-dd68-4881-8057-6c4cdd7a39a9)

<br/>

### Device Restrictions
> For **device restrictions** configure the setting manually. For more information see: [Protection Configuration Levels](https://learn.microsoft.com/nl-nl/mem/intune/fundamentals/protection-configuration-levels)

<br/>

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Devices** > **Windows** > **Configuration** and select **Create** > **New Policy**.
2. Select platform **Windows 10 and later** and profile type **Templates** > **Device Restrictions**.
3. Type the name of the profile: **bl-win-cfg-restrictions** 
4. Set **Device Restriction** for **Windows** using the following settings:   

![image](https://github.com/user-attachments/assets/d4cd42fe-54e9-422e-9fc2-293a348ab1d1)

5. Go to **Devices** > **iOS/iPadOS** > **Configuration** and select **Create** > **New Policy**.
6. Select platform **iOS/iPadOS** and profile type **Templates** > **Device Restrictions**.
7. Type the name of the profile: **bl-ios-cfg-restrictions** 
8. Set **Device Restriction** for **iOS/iPadOS** using the following settings:   

| Section | Setting | Value |
| :--- | --- | --- |
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

9. Go to **Devices** > **Android** > **Configuration** and select **Create** > **New Policy**.
10. Select platform **Android Enterprise** and profile type **Templates** > **Device Restrictions**.
11. Type the name of the profile: **bl-and-cfg-restrictions** 
12. Set **Device Restriction** for **Android Enterprise** using the following settings:   

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


## Compliance Policies
Compliance policies are commonly used in combination with Conditional Access. The Company Portal App synchronizes the device state to Intune and compares it with the compliancy policy that is targeted for the device.  

To meet with the compliancy policy that has been targeted, of course we enforce these settings first in the configuration policy. It is basically checking if those settings were applied. 

1. Use the following Protection Level for Compliance Settings:

    * [Level 2 - Enhanced device compliance settings](https://learn.microsoft.com/en-us/mem/intune/fundamentals/deployment-plan-compliance-policies#level-2---enhanced-device-compliance-settings)

2. Use the following names for the policies:

    * bl-devices-cpl-windows
    * bl-devices-cpl-ios
    * bl-devices-cpl-android

3. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Devices** > **Compliance** and create the following **Compliance Policies**:
   
![image](https://github.com/user-attachments/assets/2bf73984-88d7-4f7c-8f9b-5fb5d8561240)

## Scripts and Remediations

https://github.com/eWorkspace365/m365-landingzone/tree/main/6-microsoft-intune/mdm/powershell-scripts/Windows/Remediations

![image](https://github.com/user-attachments/assets/b63fc8e2-4a98-42aa-9a83-04c43e65cf17)

https://github.com/eWorkspace365/m365-landingzone/tree/main/6-microsoft-intune/mdm/powershell-scripts/Windows/Platform%20Scripts

![image](https://github.com/user-attachments/assets/12c98391-c425-4e6b-a80f-e97847dbfac1)



