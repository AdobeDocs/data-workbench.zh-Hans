---
description: 卸载Data Workbench的步骤地理位置。
solution: Analytics
title: 卸载Data Workbench地理位置
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 卸载Data Workbench地理位置{#uninstalling-data-workbench-geography}

卸载Data Workbench的步骤地理位置。

>[!NOTE]
>
>如果您使用Data Workbench的配置文件在Data Workbench Server群集 [!DNL Geography] 上运行，请从群集中的主Data Workbench Server中 [!DNL Geography] 卸载该配置文件。

1. 使用以下步骤更新您 [!DNL profile.cfg] 使用Data Workbench的每个配置文件的文件 [!DNL Geography]。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记， [!DNL profile.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 The [!DNL profile.cfg] window appears.

   1. 在窗 [!DNL profile.cfg] 口中，从矢量中 [!DNL Geography] 删除配置文件 [!DNL Directories] 条目。

   1. 如果您使用的是数据服务，请从矢量中删 [!DNL IP Geo-intelligence] 除或 [!DNL IP Geo-location] 配置文件 [!DNL Directories] 条目。

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL profile.cfg] 选 [!DNL User] 标记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

1. 从Data Workbench Server安装目录的Profiles文件夹中删除Geography文件夹。
1. 如果您使用的是数据服务，请从Data Workbench Server安装目录的Profiles文件夹中删除IP Geo-intelligence或IP Geo-location文件夹。
1. 从Data Workbench Server安装目录的“代码”文件夹中删除“地理”文件夹。
1. 如果您使用的是数据服务，请从Data Workbench Server安装目录的“代码”文件夹中删除“IP地理智能”或“IP地理位置”文件夹。
1. 如果您创建了新的地形图像，请从Data Workbench Server安 [!DNL Terrain Images.cfg] 装目录的“组件”文件夹中删除该文件。
