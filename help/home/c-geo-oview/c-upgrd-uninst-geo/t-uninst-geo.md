---
description: 卸载Data WorkbenchGeography的步骤。
title: 卸载 Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# 卸载 Data Workbench Geography{#uninstalling-data-workbench-geography}

卸载Data WorkbenchGeography的步骤。

>[!NOTE]
>
>如果您使用的用户档案[!DNL Geography]在Data Workbench Server群集上运行，请从群集中的主控Data Workbench Server卸载[!DNL Geography]用户档案。

1. 使用以下步骤为您使用Data Workbench [!DNL Geography]的每个用户档案更新[!DNL profile.cfg]文件。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击[!DNL profile.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 此文件的复选标记显示在[!DNL User]列中。

   1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，从[!DNL Directories]矢量中删除[!DNL Geography]用户档案条目。

   1. 如果您使用的是用户档案服务，请从[!DNL Directories]矢量中删除[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]数据项。

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL profile.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

1. 从Data Workbench Server安装目录的用户档案文件夹中删除地理文件夹。
1. 如果您使用的是用户档案服务，请从Data Workbench Server安装目录的“数据”文件夹中删除“IP地理智能”或“IP地理位置”文件夹。
1. 从Data Workbench Server安装目录的“查找”文件夹中删除“地理”文件夹。
1. 如果您使用的是数据服务，请从Data Workbench Server安装目录的“查找”文件夹中删除IP Geo-intelligence或IP Geo-location文件夹。
1. 如果您创建了新的地形图像，请从Data Workbench Server安装目录的“组件”文件夹中删除[!DNL Terrain Images.cfg]文件。
