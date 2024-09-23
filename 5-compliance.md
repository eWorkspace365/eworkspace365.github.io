[[_TOC_]]


#Information Protection

https://purview.microsoft.com/settings/application-settings/informationprotection?tid=TenantID

##Sensitivity Labels

When published, the labels you choose here will be available in specified users' Office apps (Word, Excel, PowerPoint, and Outlook), SharePoint and Teams sites, and Microsoft 365 Groups.​

**Sensitivity labels to publish**
<details>
<summary>Public (unencrypted)</summary>


Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails

Configure **Privacy** > **Access control, and other settings to protect labeled Teams, Microsoft 365 Groups, and SharePoint sites** and select:
- [X] Groups & sites

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. If the user applying the label has the correct usage rights or role, any existing access control settings will be removed from the item. 
- [X] Remove access control settings if already applied to items

Configure **Auto-labeling for files and emails** and uncheck:
- [ ] Auto-labeling for files and emails

**Define protection settings for groups and sites** and select:
- [X] Privacy and external user access
- [X] External sharing and conditional access
- [ ] Private teams discoverability and shared channel settings

**Define privacy and external user access settings** and select **Public**
For **External user access**, select:
- [X] Let Microsoft 365 Group owners add people outside your organization to the group as guests.

**Define external sharing and conditional access settings** 
Control who can share SharePoint content with people outside your organization and decide whether users can access labeled sites from unmanaged devices.​

Content can be shared with:
- [X] Anyone
For unmanaged devices configure app enforced restrictions:
- [X] Allow full access from desktop apps, mobile apps, and the web

</details>

<details>
<summary>Public (unencrypted) / Everyone </summary>

![image.png](/.attachments/image-1193c677-b7c1-49b8-9eca-8270e12303f9.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails
- [X] Meetings

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **Never**
Allow offline access, select **Always**

Apply permissions:
AuthenticatedUsers > Co-Author

</details>

<details>
<summary>Public (unencrypted) / Guests </summary>

![image.png](/.attachments/image-305f3c4f-d175-4347-bb2f-06c28a554ef1.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails
- [X] Meetings

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **A number of days after label is applied** > 90 days
Allow offline access, select **Never**

Apply permissions:
AuthenticatedUsers > Co-Author

</details>

 

<details>
<summary>External (encrypted)</summary>

![image.png](/.attachments/image-0eb23ae5-a957-409c-ab42-81e34d282638.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails

Configure **Privacy** > **Access control, and other settings to protect labeled Teams, Microsoft 365 Groups, and SharePoint sites** and select:
- [X] Groups & sites

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **Never**
Allow offline access, select **Never**

Apply permissions:
AuthenticatedUsers > Co-Author

Configure **Auto-labeling for files and emails** and uncheck:
- [ ] Auto-labeling for files and emails

**Define protection settings for groups and sites** and select:
- [X] Privacy and external user access
- [X] External sharing and conditional access
- [ ] Private teams discoverability and shared channel settings

**Define privacy and external user access settings** and select **Private**
For **External user access**, select:
- [X] Let Microsoft 365 Group owners add people outside your organization to the group as guests.

**Define external sharing and conditional access settings** 
Control who can share SharePoint content with people outside your organization and decide whether users can access labeled sites from unmanaged devices.​

Content can be shared with:
- [X] New and existing guests
For unmanaged devices configure app enforced restrictions:
- [X] Allow limited, web-only access

</details>

<details>
<summary>External (encrypted) / General</summary>

![image.png](/.attachments/image-305f3c4f-d175-4347-bb2f-06c28a554ef1.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails
- [X] Meetings

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **A number of days after label is applied** > 14 days
Allow offline access, select **Never**

Apply permissions:
AuthenticatedUsers > Viewer
*.onmicrosoft.com > Reviewer

</details>


<details>
<summary>External (encrypted) / Confidential</summary>

![image.png](/.attachments/image-305f3c4f-d175-4347-bb2f-06c28a554ef1.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails
- [X] Meetings

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **A number of days after label is applied** > 14 days
Allow offline access, select **Never**

Apply permissions:
AuthenticatedUsers > Viewer
*.onmicrosoft.com > Reviewer

</details>

<details>
<summary>Internal (encrypted)</summary>

![image.png](/.attachments/image-0eb23ae5-a957-409c-ab42-81e34d282638.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails

Configure **Privacy** > **Access control, and other settings to protect labeled Teams, Microsoft 365 Groups, and SharePoint sites** and select:
- [X] Groups & sites

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **Never**
Allow offline access, select **Always**

Apply permissions:
AuthenticatedUsers > Co-Author

Configure **Auto-labeling for files and emails** and uncheck:
- [ ] Auto-labeling for files and emails

**Define protection settings for groups and sites** and select:
- [X] Privacy and external user access
- [X] External sharing and conditional access
- [ ] Private teams discoverability and shared channel settings

**Define privacy and external user access settings** and select **Private**
For **External user access**, select:
- [X] Let Microsoft 365 Group owners add people outside your organization to the group as guests.

**Define external sharing and conditional access settings** 
Control who can share SharePoint content with people outside your organization and decide whether users can access labeled sites from unmanaged devices.​

Content can be shared with:
- [X] New and existing guests
For unmanaged devices configure app enforced restrictions:
- [X] Allow limited, web-only access

</details>

<details>
<summary>Internal (encrypted) / General</summary>

![image.png](/.attachments/image-305f3c4f-d175-4347-bb2f-06c28a554ef1.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails
- [X] Meetings

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **Never**
Allow offline access, select **Always**

Apply permissions:
*.onmicrosoft.com > Co-Owner

</details>

<details>
<summary>Internal (encrypted) / Confidential</summary>

![image.png](/.attachments/image-305f3c4f-d175-4347-bb2f-06c28a554ef1.png)

Define the scope for this label and select **Items**:
- [X] Files
- [X] Emails
- [X] Meetings

Configure **Protection settings** that will be enforced when the label is applied to items in Microsoft 365 and select:
- [X] Control Access
- [ ] Apply content marking
- [ ] Protect Teams meetings and chats

Configure **Access control**. Use encryption capabilities to control who can access labeled items. Depending on the scope you specified, items can include emails, Office, Fabric and Power BI files, and meeting invites.
- [ ] Remove access control settings if already applied to items
- [X] Configure access control settings

Assign permissions now or let users decide? Select **Assign permissions now**
User access to content expires, select **Never**
Allow offline access, select **Always**

Apply permissions:
*.onmicrosoft.com > Co-Owner

</details>

#Data Loss Prevention
https://purview.microsoft.com/settings/application-settings/datalossprevention?settingid=AutomatedTesting&tid=TenantID

##Adaptive Protection
https://purview.microsoft.com/datalossprevention/overview?tid=TenantID

![image.png](/.attachments/image-773c7308-028a-472c-8ef0-71205b800e47.png)

The following scope will be created:

![image.png](/.attachments/image-b783e130-b6c9-47e4-bbd8-3e71d65c76ac.png)

Ensure Settings are in report Only:
![image.png](/.attachments/image-e02bacc9-fa8c-4c67-92a5-b61b010ff2af.png) 

Set Alerts in DLP Policy:

Users Notification:

![image.png](/.attachments/image-824a87f9-4497-41cf-88dd-42ec23a89551.png)

Admin Notification:
![image.png](/.attachments/image-b3b3e9ba-610d-4bc0-9024-02cf9bb1d6dd.png)

#Inder Risk Management

##Settings
https://purview.microsoft.com/settings/application-settings/insiderriskmgmt?tid=TenantID

# AI Hub (Preview)
##Settings
https://purview.microsoft.com/purviewforai/overview?tid=TenantID
