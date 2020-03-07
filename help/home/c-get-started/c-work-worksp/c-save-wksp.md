---
description: 默认情况下，关闭已解锁的工作区会保存对该工作区进行的任何更改。
solution: Analytics
title: 保存工作区
topic: Data workbench
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 保存工作区{#save-a-workspace}

默认情况下，关闭已解锁的工作区会保存对该工作区进行的任何更改。

如果工作区是服务器工作区，则您所做的更改将仅保存在本地，除非您专门将更新的工作区保存到Data Workbench Server。 有关锁定工作区的详细信息，请参阅解 [锁工作区](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)。

## 将工作区保存在本地 {#section-3f331c880f1a490c96844103c2432d61}

The default save location is the **User\profile name\Workspaces\tab name** folder within the Data Workbench installation directory. For example, if you are working with the Movies profile and you save a workspace locally from the [!UICONTROL Custom] tab, the workspace is saved to the **User\Movies\Workspaces\Custom** folder in your Data Workbench installation directory.

**保存对工作区的更改**

* In the workspace, click **[!UICONTROL File]**, then **[!UICONTROL Save]**.

**将现有工作区另存为新工作区**

1. 在所需的 [!DNL Worktop] 选项卡上，单击要显示的工作区的缩略图。
1. 在工作区中，单击， **[!UICONTROL File]**&#x200B;然后单击 **[!UICONTROL Save Copy As]**。
1. In the [!DNL Save Workspace As] dialog box, specify the name and location where you want to save the copied workspace and click **[!UICONTROL Save]**.

## Save a workspace to the Data Workbench server {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>只有具有相应权限的用户才能将工作区保存到Data Workbench服务器。 有关详细信息，请与您的系统管理员联系。

将工作区保存到连接的Data Workbench Server也称为发布工作区，因为它使工作区对其他用户可用。 By default, workspaces are saved to the *working profile name*\Workspaces\*tab name* folder of the Data Workbench server. For example, if you are working with the Movies profile and you save a workspace to the connected Data Workbench server from the [!DNL Custom] tab, the workspace is saved to the Movies\Workspaces\Custom folder of the Data Workbench server.

**将工作区保存到Data Workbench Server**

* On the desired [!DNL Worktop] tab, right-click the thumbnail of the workspace that you want to save to the Data Workbench server and click **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
