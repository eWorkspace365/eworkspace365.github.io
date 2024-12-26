# Table of Contents
   * [Azure](#azure)
      * [1. EntraID](#1-entraid)
      * [2. Compute Resources](#2-compute-resources)
      * [3. Monitor and Backup](#3-monitor-and-backup)
      * [4. Storage and Databases](#4-storage-and-databases)
      * [5. Virtual Networking](#5-virtual-networking)
   * [Microsoft 365](#microsoft-365)
     * [1. Cloud Adoption](#1-cloud-adoption)
     * [2. Networking](#2-networking)
     * [3. Identity](#3-identity)
     * [4. Security](#4-security)
     * [5. Compliance](#5-compliance)
     * [6. Microsoft Intune](#6-microsoft-intune)
     * [7. Monitoring](#7-monitoring)
     * [8. Roadmap](#8-roadmap)


# Azure

## 1. EntraID

## 2. Compute Resources

## 3. Monitor and Backup

## 4. Storage and Databases

## 5. Virtual Networking


# Microsoft 365

## 1. Cloud Adoption

## 2. Networking

## 3. Identity

## 4. Security

## 5. Compliance

## 6. Microsoft Intune


### EndPoint Privileged Management

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Endpoint security** > **Endpoint Privilege Management** > select the **Policies** tab > and then select **Create Policy**.
   Set the *Platform* to **Windows**, *Profile* to **Windows elevation settings policy**, and then select **Create**.

2. On **Basics**, enter the following properties:

   - **Name**: bl-win-cfg-privilege-mgmt
   - **Assignments**: All Users

![image](https://github.com/user-attachments/assets/e65829b8-b41f-4f23-87aa-39ef8f0d2db1)


Microsoft documentation: https://learn.microsoft.com/en-us/mem/intune/protect/epm-overview


## 7. Monitoring

## 8. Roadmap




https://docs.github.com/en/get-started/start-your-journey/about-github-and-git

https://www.markdownguide.org/getting-started

[Conditional Access](3-identity.md).

[Compliance](5-compliance.md).

![image](https://github.com/user-attachments/assets/bd01b82c-3033-4614-9027-6427e2f7cf95)





# Microsoft | Secure and Compliant Baseline Configuration

![image](https://github.com/klieka/klieka.github.io/assets/168641483/7702be10-bc4a-4f45-ba83-86a616f7748d)



[Menu Item 1]()

  * # SubMenu Heading 1
  * [6. Microsoft Intune](6-microsoft-intune.md)
  * [SubMenu Item 2](subitem2.md)
  - - - -
  * # SubMenu Heading 2
  * [SubMenu Item 3](subitem3.md)
  - - - -
  * # SubMenu Heading 3
  * [SubMenu Item 3](subitem3.md)

[Menu Item 2](item2.md)
- - - -
[Menu Item 3](item3.md)

![image](https://github.com/klieka/klieka.github.io/assets/168641483/49165fff-620a-42d4-bf46-492bd5fba0f1)

# Windows 10/11
---
1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. Go to **Devices** > **Compliance** and choose **Create policy**.

1. Select a Platform for this policy:

   - **Windows 10 and later**

1. Name for this policy:

   - **BL-COBO-WIN-DEV-CPL-Personal-Desktop**
   
     ![image.png](/.attachments/image-f87132d7-69ab-4aa0-b34e-aba5984a9760.png)

1. Set action "Mark device noncompliant" to schedule: 

   - **Immediately**

1. Set the following settings:

   | Description | Setting | 
   |-----------|:-----------:|
   | Require a password to unlock mobile devices | **Required** |
   | Simple passwords | **Block** |  
   | Required password type | **At least alphanumeric** | 
   | Minimum password length | **6** | 
   | Maximum minutes of inactivity before password is required | **5 minutes** | 
   | Require encryption of data storage on device | **Required** | 
   | Firewall | **Required** | 
   | Trusted Platform Module (TPM) | **Required** | 
   | Antivirus | **Required** | 
   | Antispyware | **Required** | 
   | Microsoft Defender Antimalware | **Required** | 
   | Microsoft Defender Antimalware security intelligence up-to-date | **Required** |
   | Real-time protection | **Required** | 
   | Require the device to be at or under the machine risk score | **Medium** | 

# MacOS
----
1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. Go to **Devices** > **Compliance** and choose **Create policy**.

1. Select a Platform for this policy:

   - **macOS**

1. Name for this policy:

   - **BL-COBO-MAC-DEV-CPL-Personal-Desktop**

   ![image.png](/.attachments/image-d999709c-7a39-44cd-9187-2ed0e12de44e.png)

1. Set action "Mark device noncompliant" to schedule: 

   - **Immediately**

1. Set the following settings:

   | Description | Setting | 
   |-----------|:-----------:|
   | Require system integrity protection | **Required** |
   | Require a password to unlock mobile devices | **Required** |  
   | Simple passwords | **Block** |
   | Required password type | **At least alphanumeric** | 
   | Minimum password length | **8** | 
   | Maximum minutes of inactivity before password is required | **5 minutes** | 
   | Require encryption of data storage on device | **Required** | 
   | Firewall | **Required** | 
   | Incoming connections | **Block** | 
   | Stealth Mode | **Enabled** | 
   | Allow apps downloaded from these locations | **Mac App Store** | 

# Android
----
1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. Go to **Devices** > **Compliance** and choose **Create policy**.

1. Select a Platform for this policy:

   - **Android Enterprise**

1. Name for this policy:

   - **BL-COBO-AND-DEV-CPL-Personal-Device**

   ![image.png](/.attachments/image-7d7f7531-9a5c-4215-a766-48612e7d98f6.png)

1. Set action "Mark device noncompliant" to schedule: 

   - **Immediately**

1. Set the following settings:

   | Description | Setting | 
   |-----------|:-----------:|
   | Require a password to unlock mobile devices | **Required** |
   | Required password type | **At least alphanumeric** | 
   | Minimum password length | **6** | 
   | Maximum minutes of inactivity before password is required | **5 minutes** | 
   | Require encryption of data storage on device | **Required** | 
   | Require the device to be at or under the machine risk score | **Medium** | 

# iOS
----
1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. Go to **Devices** > **Compliance** and choose **Create policy**.

1. Select a Platform for this policy:

   - **iOS/iPadOS**

1. Name for this policy:

   - **BL-COBO-IOS-DEV-CPL-Personal-Device**

   ![image.png](/.attachments/image-1aeb753a-7a23-4c9b-9fab-adec23443082.png)
1. Set action "Mark device noncompliant" to schedule: 

   - **Immediately**

1. Set the following settings:

   | Description | Setting | 
   |-----------|:-----------:|
   | Require the device to be at or under the Device Threat Level | **Secured** |
   | Jailbroken devices | **Block** | 
   | Require a password to unlock mobile devices | **Required** | 
   | Simple passwords | **Block** | 
   | Minimum password length | **6** | 
   | Required password type | **6** | **At least numeric**
   | Maximum minutes after screen lock before password is required | **5 minutes** | 
   | Maximum minutes of inactivity until screen locks | **5 minutes** | 
   | Require the device to be at or under the machine risk score | **Medium** | 
