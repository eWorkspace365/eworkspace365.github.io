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

