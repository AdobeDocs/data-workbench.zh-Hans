---
description: 卸载Data WorkbenchGeography的步骤。
title: 卸载 Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# 卸载 Data Workbench Geography{#uninstalling-data-workbench-geography}

{{eol}}

卸载Data WorkbenchGeography的步骤。

>[!NOTE]
>
>如果您使用Data Workbench的用户档案 [!DNL Geography] 在data workbench server群集上运行，请卸载 [!DNL Geography] 群集中主控data workbench server的配置文件。

1. 请按照以下步骤更新 [!DNL profile.cfg] 用于您使用Data Workbench的每个配置文件的文件 [!DNL Geography].

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记 [!DNL profile.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 的 [!DNL profile.cfg] 窗口。

   1. 在 [!DNL profile.cfg] 窗口，删除 [!DNL Geography] 用户档案条目 [!DNL Directories] 矢量图。

   1. 如果您一直在使用数据服务，请删除 [!DNL IP Geo-intelligence] 或 [!DNL IP Geo-location] 用户档案条目 [!DNL Directories] 矢量图。

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，右键单击的复选标记 [!DNL profile.cfg] 在 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. 从Data Workbench Server安装目录的Profiles文件夹中删除Geography文件夹。
1. 如果您使用的是数据服务，请从Data Workbench Server安装目录的Profiles文件夹中删除IP地理智能或IP地理位置文件夹。
1. 从Data Workbench Server安装目录的“查找”文件夹中删除Geography文件夹。
1. 如果您之前使用过数据服务，请从Data Workbench Server安装目录的“查找”文件夹中删除IP地理智能或IP地理位置文件夹。
1. 如果创建了新地形图像，请删除 [!DNL Terrain Images.cfg] 文件。
