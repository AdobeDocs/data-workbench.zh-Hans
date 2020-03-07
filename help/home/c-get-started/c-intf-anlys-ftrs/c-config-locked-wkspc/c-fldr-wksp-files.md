---
description: 在Data Workbench安装目录的Workspaces文件夹中，folder.lock文件指定是否锁定该特定文件夹中的工作区，而工作区名称。lock文件指定是否锁定特定工作区。
solution: Analytics
title: Folder.lock和workspace.lock文件
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Folder.lock and workspace.lock files{#folder-lock-and-workspace-lock-files}

在Data Workbench安装目录的Workspaces文件夹中，folder.lock文件指定是否锁定该特定文件夹中的工作区，而工作区名称。lock文件指定是否锁定特定工作区。

当锁定整个文件夹时，您可以在 Workspaces 文件夹级别或子文件夹（选项卡）级别锁定它们。您还可以锁定或解除锁定所有的文件夹（在 Workspaces 文件夹级别），然后指定特定子文件夹（使用 [!DNL folder.lock] 文件）或特定工作区（使用&#x200B;*工作区名称*.lock 文件）的例外情况。

The following example of the [!DNL Profile Manager] highlights three elements:

* 主 Workspaces 文件夹对应的 [!DNL folder.lock] 文件
* A [!DNL Monthly Numbers.lock] file for the [!DNL Monthly Numbers.vw] workspace file

* Workspaces\Custom 子文件夹对应的 [!DNL folder.lock] 文件

![](assets/wsp_Locking_lockFiles.png)

In this example, the [!DNL Workspaces folder.lock] file is set to locked, which locks all of the workspaces in this instance of Data Workbench. Workspaces\ 子文件夹 [!DNL folder.lock] 文件被设置为已解锁，这将解除锁定“[!DNL Custom]自定义”选项卡上的所有工作区。最后，[!DNL Monthly Numbers.lock] 文件被设置为已锁定，这将锁定 Monthly Numbers 工作区。

## 创建 .lock 文件 {#section-c4f78b4b43c347368a376904effb41d2}

您可以使用 [!DNL new folder.lock] 或中的 [!DNL Create menu] 选项创建 [!DNL Profile Manager] 文件 [!DNL Workspaces Manager]。 You also can create a [!DNL folder.lock] or *workspace name*.lock file by copying and pasting an existing [!DNL .lock] file to the appropriate folder, changing the name of the file (for *workspace name*.lock files only), and changing the setting in the file if necessary.

**创建新的 folder.lock 文件**

1. 在Data Workbench中，通过在工 [!DNL Workspaces Manager] 作区中右键单击并单击 **[!UICONTROL Manage]** > **[!UICONTROL Profile]** >打开 **[!UICONTROL Workspaces Manager]**。
1. 单击您想要创建 [!DNL folder.lock] 文件的文件夹。
1. In the [!DNL User] column for that folder, right-click in the cell and click **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. 将出 [!DNL new folder.lock] 现文件。 [!DNL New folder.lock] 默认情况下，文件设 [置为] “已解锁”。
1. （可选）如果您需要更改文件中的设置：

   1. 右键单击该文件的复选标记。
   1. 单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL folder.lock] file opens.

   1. Change the setting to [locked].
   1. 保存并关闭该文件。

1. To make this the setting for all users working with the same working profile, right-click the check mark for the file and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

根据新文件中的设置，该文件夹中的工作区现已锁定或解锁。

**从现有文件中创建 .lock 文件**

1. 在或 [!DNL Profile Manager] 中， [!DNL Workspaces Manager]右键单击现有文件的复选标记， [!DNL .lock] 然后单击 **[!UICONTROL Copy]**。
1. In the [!DNL User] column for the folder into which you want to paste the [!DNL .lock] file, right-click in the cell and click **[!UICONTROL Paste]**.
1. If this file is used to lock an individual workspace, right-click the check mark for the [!DNL .lock] file in the [!DNL User] column and change its name in the [!DNL File] field to match the name of the workspace that you want to lock.

   For example, to lock the [!DNL Monthly Numbers.vw] workspace, you would name the file “ [!DNL Monthly Numbers.lock].”If this file is used to lock an individual workspace, right-click the check mark for the [!DNL .lock] file in the [!DNL User] column and change its name in the [!DNL File] field to match the name of the workspace that you want to lock. For example, to lock the [!DNL Monthly Numbers.vw] workspace, you would name the file “ [!DNL Monthly Numbers.lock].”

1. 若要更改文件中的设置：

   1. 右键单击该文件的复选标记。
   1. 单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL .lock] file opens.

   1. Change the setting to [locked] or [unlocked].
   1. 保存并关闭该文件。

1. To make this the setting for all users working with the same working profile, right-click the check mark for the file and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

根据新文件中的设置，选定工作区现已锁定或解锁。
