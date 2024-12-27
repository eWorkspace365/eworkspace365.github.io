# Mobile Application Management (MAM)

### In this article
>  * [Apps Deployment](m365-6-1-tenant-administration.md)
>   * [Apps Configuration)](#mobile-application-management-mam)
>   * [Apps Monitor](#mobile-device-management-mdm)

## Apps Deployment

### Microsoft Store App
1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **All apps** and select **Add**.
2. Select **App type** > **Microsoft Store app**
3. Edit for all assigments **Group mode** > **Required**
4. Add all the following **Microsoft Store apps** and assign them to baseline group **bl-sg-devices-windows-mdm**.
  
![image](https://github.com/user-attachments/assets/a02d692b-e745-4d56-99a7-6db6a0571b46)


### Windows App (Win32)

> [!IMPORTANT]
> - [X] https://github.com/Microsoft/Microsoft-Win32-Content-Prep-Tool
> - [X] [Winget-Package-Deployment.ps1](https://www.google.nl)



## Deploy Application
Install command:
`powershell -executionpolicy bypass -file winget-package-deployment.ps1 "install" "Jabra Direct"`

Uninstall command:
`powershell -executionpolicy bypass -file winget-package-deployment.ps1 "uninstall" "Jabra Direct"`

![image](https://github.com/user-attachments/assets/9af95f9e-5110-4ea0-8410-ae09777bf3d7)


Detection Rule:
Configure the following detection rule forthe application:

![image.png](/.attachments/image-d543bf81-5469-4be5-896d-bc1128e490dd.png)

##Assignment Policy
Use the following method to correctly assign the application to the corresponding application group. 

![image.png](/.attachments/image-869f1053-27c7-41b0-ba03-c47b42f0dcd9.png)




## Apps Configuration


## Apps Monitor




##Update Policy
- [X] [Deploy Store-app Winget-AutoUpdate-aaS](https://apps.microsoft.com/detail/xp89bsk82w9j28?amp%3Bgl=US&hl=en-us&gl=NL) 
- [X] [Configure Winget-AutoUpdate ADMX templates](https://github.com/Romanitho/Winget-AutoUpdate/tree/main/Sources/Policies/ADMX) 

![image.png](/.attachments/image-4e1022c5-7c6a-4b60-8d72-653acd019686.png)
