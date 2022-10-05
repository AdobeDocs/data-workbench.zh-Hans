---
description: 这些步骤仅适用于创建工作区窗口菜单的子菜单和菜单项。
title: 创建工作区菜单和菜单项
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 28%

---

# 创建工作区菜单和菜单项{#create-a-workspace-menu-and-menu-item}

{{eol}}

这些步骤仅适用于创建工作区窗口菜单的子菜单和菜单项。

您可以通过创建新文件夹和新的派生量度和维度来自定义量度和维度菜单。有关详细信息，请参阅 [创建和编辑派生量度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) 和 [创建和编辑派生Dimension](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**创建新的工作区窗口菜单**

1. 在 [!DNL Profile Manager]，请单击 **[!UICONTROL Menu]** 目录查看其内容。
1. 在 [!DNL User] 列，单击 **[!UICONTROL Create]** > **[!UICONTROL Folder]**. 在 [!DNL File] 列 [!DNL Menu].

   >[!NOTE]
   >
   >您还可以为Menu目录中的任何子目录创建新文件夹。

1. 在 [!DNL User] 列，然后在Dir参数中键入新名称。
1. 向新文件夹添加所需文件。
1. （可选）在 [!DNL User] 列，单击 **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   安 [!DNL order.txt] 文件会显示在 [!DNL File] 列中，并且新文件的复选标记会显示在 [!DNL User] 列。

1. （可选）根据需要编辑 [!DNL order.txt] 文件。请参阅 [使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. （可选）若要使更改对工作配置文件的所有用户可用，请右键单击 [!DNL User] 列，单击 **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**向现有菜单添加一个新菜单项**

1. 完成以下步骤之一：

   * 创建一个要添加到菜单中的新项目（可视化、批注等等）：

      1. 在Data Workbench中打开工作区并创建所需的项目。
      1. 将该项目保存到以下目录：

         *Data Workbench安装目录*\User\*工作配置文件名称*\Work

      1. 在 [!DNL Profile Manager]，请单击 **[!UICONTROL Work]** 目录查看其内容。
      1. 在 [!DNL User] 列中，右键单击所需文件的复选标记，然后单击 **[!UICONTROL Copy]**.
      1. 在 [!DNL User] 列，单击 **[!UICONTROL Paste]**.

         文件的副本将显示在 [!DNL File] 列中，并且新文件的复选标记会显示在 [!DNL User] 列。
   * 在菜单（文件夹）之间复制和粘贴现有项目：

      1. 在 [!DNL Profile Manager]，请单击 **[!UICONTROL Menu]** 目录查看其内容。
      1. 在 *工作配置文件名称* 列中，右键单击所需文件的复选标记，然后单击 **[!UICONTROL Make Local]**.
      1. 右键单击 [!DNL User] 列，单击 **[!UICONTROL Copy]**.
      1. 在 [!DNL User] 列，单击 **[!UICONTROL Paste]**. 文件的副本将显示在 [!DNL File] 列中，并且新文件的复选标记会显示在 [!DNL User] 列。


1. （可选）根据需要编辑 [!DNL order.txt] 文件。请参阅 [使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. （可选）若要使更改对工作配置文件的所有用户可用，请右键单击 [!DNL User] 列，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. （可选）为避免在多个菜单中显示菜单项，应通过右键单击 *工作配置文件名称* 列，单击 **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   对 [!DNL User] 列。
