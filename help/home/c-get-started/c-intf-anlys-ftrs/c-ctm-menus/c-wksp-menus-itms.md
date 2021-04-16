---
description: 这些步骤仅适用于创建工作区窗口菜单的子菜单和菜单项。
title: 创建工作区菜单和菜单项
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 28%

---

# 创建工作区菜单和菜单项{#create-a-workspace-menu-and-menu-item}

这些步骤仅适用于创建工作区窗口菜单的子菜单和菜单项。

您可以通过创建新文件夹和新的派生量度和维度来自定义量度和维度菜单。有关详细信息，请参阅  [创建和编辑派生](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) 量度 [以及创建和编辑派生Dimension](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)。

**创建新的工作区窗口菜单**

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Menu]**&#x200B;目录以视图其内容。
1. 在Menu目录的[!DNL User]列中，单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Folder]**。 [!DNL Menu]的[!DNL File]列中将显示名为New Folder的文件夹。

   >[!NOTE]
   >
   >您还可以为Menu目录中的任何子目录创建新文件夹。

1. 在文件夹的[!DNL User]列中右键单击并在Dir参数中键入新名称，即可重命名新文件夹。
1. 向新文件夹添加所需文件。
1. （可选）在新文件夹的[!DNL User]列中，单击&#x200B;**[!UICONTROL Create]** > **[!UICONTROL order.txt]**。

   新文件夹的[!DNL File]列中会显示一个[!DNL order.txt]文件，而[!DNL User]列中会显示新文件的复选标记。

1. （可选）根据需要编辑 [!DNL order.txt] 文件。请参阅[使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。
1. （可选）要使更改对工作用户档案的所有用户可用，请右键单击[!DNL User]列中文件夹的白色复选标记，然后单击&#x200B;**[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*。

**向现有菜单添加一个新菜单项**

1. 完成以下步骤之一：

   * 创建一个要添加到菜单中的新项目（可视化、批注等等）：

      1. 在Data Workbench中打开工作区并创建所需项。
      1. 将该项目保存到以下目录：

         *Data Workbench安装目录*\User\*工作用户档案名称*\Work

      1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Work]**&#x200B;目录以视图其内容。
      1. 在[!DNL User]列中，右键单击所需文件的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。
      1. 在所需文件夹的[!DNL User]列中，单击&#x200B;**[!UICONTROL Paste]**。

         新文件夹的[!DNL File]列中会显示该文件的副本，而[!DNL User]列中会显示该新文件的复选标记。
   * 在菜单（文件夹）之间复制和粘贴现有项目：

      1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Menu]**&#x200B;目录以视图其内容。
      1. 在&#x200B;*工作用户档案名称*&#x200B;列中，右键单击所需文件的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。
      1. 右键单击[!DNL User]列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Copy]**。
      1. 在所需文件夹的[!DNL User]列中，单击&#x200B;**[!UICONTROL Paste]**。 新文件夹的[!DNL File]列中会显示该文件的副本，而[!DNL User]列中会显示该新文件的复选标记。


1. （可选）根据需要编辑 [!DNL order.txt] 文件。请参阅[使用Order.txt文件自定义菜单](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。
1. （可选）要使更改对工作用户档案的所有用户可用，请右键单击[!DNL User]列中每个文件的白色复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。
1. （可选）为避免菜单项出现在多个菜单中，您应从其原始文件夹中删除相应文件，方法是右键单击&#x200B;*工作用户档案名称*&#x200B;列中文件的复选标记，然后单击&#x200B;**[!UICONTROL Remove]** > **[!UICONTROL Yes]**。

   对[!DNL User]列中文件的复选标记重复此步骤。
