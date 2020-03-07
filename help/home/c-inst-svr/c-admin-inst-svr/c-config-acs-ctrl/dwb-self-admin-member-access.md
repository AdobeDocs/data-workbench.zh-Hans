---
description: 管理员可以向工作站用户授予部分权限，允许其管理自定义群组的访问控制。
title: 群组成员访问权限的用户管理
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 群组成员访问权限的用户管理{#user-administration-of-group-member-access}

管理员可以向工作站用户授予部分权限，允许其管理自定义群组的访问控制。

**群组成员访问权限的自我管理**&#x200B;为非管理员用户提供了在自定义群组中添加和删除成员权限的能力。管理员可以在 **Access Control.cfg** 文件中为新增的群组成员创建 [User List](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) 文件并设置群组访问权限。

**访问服务器管理器**

Setting up the **[!DNL User List]** file and synching it with the **[!DNL Communications.cfg]** file is done in the **Servers Manager** workspace.

1. 在工作台上，单击&#x200B;**管理员**&#x200B;选项卡 >**数据集和配置文件**&#x200B;选项卡。

1. 打开&#x200B;**服务器管理器**&#x200B;工作区。
1. 在图中右键单击 &lt;*您的服务器名称*>，然后选择&#x200B;**文件**。

   The server files will open in a table with columns *File*, *`<server name>`*, and *Temp*.

1. **通过右键单击服务器文件** （针对此功能和）的服务器列，制作本地 **[!DNL Access Control]** 文件 **[!DNL Components/Communications.cfg)]**。

   此刻，**临时**&#x200B;列中将会显示一个白色复选标记。您可以在“临时”文件夹中进行编辑。然后右键单击复选标记，**保存到**&#x200B;服务器中。（与服务器进行同步时，它会变为红色。）

## 创建一个 User List.cfg 文件 {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

The administrator needs to create a **[!DNL User List.cfg]** file in the **[!DNL Access Control]** folder.

1. Right-click** Access Control** row in the **Temp** column and select **Open** > **Folder**. ![](assets/6_4_workstation_groups_3.png)

   **Temp** 文件夹中的 Access Control 文件夹将会打开，其中列出了 **[!DNL Access Control.cfg]** 文件。

1. Add another text file to this folder and name it **[!DNL User List.cfg]** (next to the **[!DNL Access Control.cfg]**).

1. Add the following parameters to the **[!DNL User List.cfg]** file.

User List 文件应当包含一个 **AccessGroup** 对象的矢量，每个 **AccessGroup** 对象都应该具有一个名称和一个称之为 **Members** 的字符串矢量。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

You can then edit and add users this in the Workstation view of the **[!DNL User List.cfg]**file.

![](assets/6_4_workstation_groups_4.png)

Here&#39;s the most basic parameters to add to the **[!DNL User List.cfg]** file. 随后，可以在工作站视图中添加成员。

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>As with any **[!DNL .cfg]** file that you manually edit, make sure to use spaces instead of tabs and to pay close attention to the whitespace and syntax. 如果该文件出现错误，则会导致 *Adobe Insight Server* 忽略 User List 文件。

每个&#x200B;**访问群组**&#x200B;中的&#x200B;**名称**&#x200B;字段将被引用在 [!DNL Access Control.cfg] 文件中。

>[!NOTE]
>
>Only valid members with directory service prefixes, such as **CN:** or **OU:** are accepted, and these cannot contain wildcard character (*).

## 设置 Communications.cfg 文件 {#section-9d6f05ba81c14f15be63e361533459e8}

An administrator first enables this feature by opening the **[!DNL Components]>[!DNL Communications.cfg]**file and adding a new key with the name **[!DNL Access Control User List File]**. 这个键的字符串值就是将要存储该新文件的路径。

1. 从服务器文件中，单击&#x200B;**组件**，然后右键单击服务器列中的复选标记。单击&#x200B;**制作本地副本**。

   此刻，**临时**&#x200B;列中将会显示一个白色复选标记。

1. 右键单击&#x200B;**临时**&#x200B;列中的复选标记，然后选择&#x200B;**打开** > **在工作站中**。

1. 在 **Communication.cfg** 文件中，右键单击&#x200B;**组件**，然后选择&#x200B;**添加自定义键**。 ![](assets/6_4_workstation_groups.png)

1. 在&#x200B;**名称**&#x200B;中键入 *Access Control User List File*，然后将&#x200B;**类型**&#x200B;设置为 *String*。

   >[!NOTE]
   不能将新列表文件创建为路径。 若要纠正这个问题，您需要保存文件，然后在编辑器（记事本）中打开该文件，将“String”更改为“Path”：

   之前：

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   之后：

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. 保存 **[!DNL Communications.cfg]** 文件，（如有必要）将它保存到服务器中。这将会在服务器中重新启动组件，以确保您没有产生任何错误，导致阻止解析 **[!DNL Communications.cfg]** 文件。
1. If your system includes processing servers, modify the configuration file in the **[!DNL Components for Processing Servers.cfg]** file.
1. Right-click **[!DNL Communications.cfg]** and save to server.

现在，Data Workbench 管理员可以确认目标用户具有 User List 文件的访问权限，并且允许用户管理该群组。这些用户将可以打开 User List 文件、对其进行编辑，并且可以根据需要，添加和删除 CN 或 OU 成员。

## 同步 Access Control.cfg 文件 {#section-ca6da453dfb4432bb40b86ef15ede872}

管理员可以编辑 **[!DNL Access Control.cfg]**，并将引用插入到由 *User List* 文件定义的群组中。

应当像任何其他成员一样，插入对群组的引用，不过，应使用下面的语法：

```
$(Group Name)
```

“群组名称”应当与 User List 文件中定义的内容相同，包括空格。 ![](assets/6_4_workstation_groups_2.png)

此时，Data Workbench 管理员可以确认选定的群组用户具有 User List 文件的访问权限。接下来，选定的用户就可以打开 **[!DNL User List.cfg]** 文件、对其进行编辑，并且可以根据需要，添加和删除 CN 或 OU 成员。
