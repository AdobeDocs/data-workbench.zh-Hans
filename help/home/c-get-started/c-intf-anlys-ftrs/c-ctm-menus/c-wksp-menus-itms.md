---
description: 这些步骤仅适用于创建工作区窗口菜单的子菜单和菜单项。
solution: Analytics
title: 创建工作区菜单和菜单项
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 创建工作区菜单和菜单项{#create-a-workspace-menu-and-menu-item}

这些步骤仅适用于创建工作区窗口菜单的子菜单和菜单项。

您可以通过创建新文件夹和新的派生量度和维度来自定义量度和维度菜单。有关详细信息，请参阅 创 [建和编辑派生量度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) ，创 [建和编辑派生维度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)。

**创建新的工作区窗口菜单**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents.
1. 在“菜 [!DNL User] 单”目录的列中，单击 **[!UICONTROL Create]** > **[!UICONTROL Folder]**。 A folder named New Folder appears in the [!DNL File] column for [!DNL Menu].

   >[!NOTE]
   >
   >您还可以为Menu目录中的任何子目录创建新文件夹。

1. Rename the new folder by right-clicking in the [!DNL User] column for the folder and typing the new name in the Dir parameter.
1. 向新文件夹添加所需文件。
1. (Optional) In the [!DNL User] column for the new folder, click **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   An [!DNL order.txt] file appears in the [!DNL File] column for the new folder, and a check mark for the new file appears in the [!DNL User] column.

1. （可选）根据需要编辑 [!DNL order.txt] 文件。See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for the folder in the [!DNL User] column and click **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**向现有菜单添加一个新菜单项**

1. 完成以下步骤之一：

   * 创建一个要添加到菜单中的新项目（可视化、批注等等）：

      1. 在Data Workbench中打开工作区，然后创建所需的项目。
      1. 将该项目保存到以下目录：

         *Data Workbench安装目录*\User\*工作配置文件名称*\Work

      1. In the [!DNL Profile Manager], click the **[!UICONTROL Work]** directory to view its contents.
      1. In the [!DNL User] column, right-click the check mark for the desired file and click **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

         A copy of the file appears in the [!DNL File] column for the new folder, and a check mark for the new file appears in the [!DNL User] column.
   * 在菜单（文件夹）之间复制和粘贴现有项目：

      1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents.
      1. In the *working profile name* column, right-click the check mark for the desired file and click **[!UICONTROL Make Local]**.
      1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. A copy of the file appears in the [!DNL File] column for the new folder, and a check mark for the new file appears in the [!DNL User] column.


1. （可选）根据需要编辑 [!DNL order.txt] 文件。See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for each file in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Optional) To avoid having a menu item appear in multiple menus, you should delete the corresponding file from its original folder by right-clicking the check mark for the file in the *working profile name* column and clicking **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repeat this step for the file’s check mark in the [!DNL User] column.

