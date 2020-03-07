---
description: 随Data WorkbenchGeography一起提供的地理位置配置文件是一个内部配置文件，它为您的Adobe应用程序提供了其他功能。
solution: Analytics
title: 安装地理位置配置文件
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装地理位置配置文件{#installing-the-geography-profile}

随Data WorkbenchGeography一起提供的地理位置配置文件是一个内部配置文件，它为您的Adobe应用程序提供了其他功能。

与Adobe提供的所有其他内部配置文件一样， [!DNL Geography] 不应更改该配置文件。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

该配 [!DNL Geography] 置文件包括若干定义地理维度的转换数据集包含 [!DNL Dataset\Transformation\Geography] 文件（位于文件夹中）。 以下是随配置文件提供的转换数据集包含文件的 [!DNL Geography] 列表：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每个文件都以它定义的扩展维命名。 另一个文件定 [!DNL IPLookup.cfg]义几个地理数据字段，这些字段用于定义其他转换数据集包含文件中的维度。

For information about transformation dataset include files, see the *Dataset Configuration Guide*.

**在Data Workbench Server上[!DNL Geography]安装配置文件的步骤**

>[!NOTE]
>
>以下安装说明假定您已安装Data Workbench，并且已在Data Workbench与要安装Data Workbench的Data Workbench Server之间建立了连接 [!DNL Geography]。 如果尚未执行此操作，请参阅《 *Data Workbench用户指南》*。

1. 从Adobe提供给您的文 [!DNL .zip] 件中打开Profiles文件夹。
1. 将该文 [!DNL Geography] 件夹复制到Data Workbench Server安装目录中的Profiles文件夹。 您希望最终在Data Workbench Server上 [!DNL ...\Profiles\Geography] 显示一个文件夹，如以下示例所示。 Profiles文件夹中其他文件夹的名称可能与显示的文件夹不同。

   ![步骤信息](assets/Geo_installProfiles_dir.png)

1. 请按照以下步骤为要使 [!DNL profile.cfg] 用Data Workbench的每个配置文件更新文件 [!DNL Geography]。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记， [!DNL profile.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 The [!DNL profile.cfg] window appears.

   1. 在窗 [!DNL profile.cfg] 口中，右键单击并 **[!UICONTROL Directories]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要将新目录添加到目录列表的末尾，请右键单击列表中最后一个目录的编号或名称，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称： [!DNL Geography].
   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在列 [!DNL Profile Manager]中，右键单击列中的复 [!DNL profile.cfg] 选 [!DNL User] 标记，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL Geography] profile), as your changes are overwritten when you install updates to these profiles.

