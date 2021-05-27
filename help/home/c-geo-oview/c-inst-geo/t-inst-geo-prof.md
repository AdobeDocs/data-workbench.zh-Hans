---
description: 随Data WorkbenchGeography一起提供的地理位置配置文件是一个内部配置文件，可为您的Adobe应用程序提供附加功能。
title: 安装地理位置配置文件
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 6%

---

# 安装地理位置配置文件{#installing-the-geography-profile}

随Data WorkbenchGeography一起提供的地理位置配置文件是一个内部配置文件，可为您的Adobe应用程序提供附加功能。

与Adobe提供的所有其他内部配置文件一样，不应更改[!DNL Geography]配置文件。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

[!DNL Geography]配置文件包含多个定义地理维度的转换数据集包含文件（位于[!DNL Dataset\Transformation\Geography]文件夹中）。 以下是随[!DNL Geography]配置文件提供的转换数据集包含文件的列表：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每个文件都针对它定义的扩展维度进行命名。 另一个文件[!DNL IPLookup.cfg]定义了几个地理数据字段，这些字段用于定义其他转换数据集包含文件中的维度。

有关转换数据集包含文件的信息，请参阅《数据集配置指南》*。*

**在Data Workbench Server上 [!DNL Geography] 安装配置文件**

>[!NOTE]
>
>以下安装说明假定您已安装Data Workbench，并在Data Workbench与要在其上安装Data Workbench [!DNL Geography]的Data Workbench Server之间建立了连接。 如果尚未这样做，请参阅&#x200B;*Data Workbench用户指南*。

1. 从[!DNL .zip]文件中打开由Adobe提供给您的Profiles文件夹。
1. 将[!DNL Geography]文件夹复制到Data Workbench Server安装目录的Profiles文件夹中。 您希望在Data Workbench Server上最终显示[!DNL ...\Profiles\Geography]文件夹，如以下示例所示。 Profiles文件夹中其他文件夹的名称可能与显示的名称不同。

   ![步骤信息](assets/Geo_installProfiles_dir.png)

1. 请按照以下步骤为要使用Data Workbench [!DNL Geography]的每个配置文件更新[!DNL profile.cfg]文件。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击[!DNL profile.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。

   1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，右键单击&#x200B;**[!UICONTROL Directories]** ，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要将新目录添加到目录列表末尾，请右键单击列表中最后一个目录的编号或名称，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 键入新目录的名称：[!DNL Geography]。
   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL profile.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >请勿将修改的配置文件保存到由Adobe提供的任何内部配置文件（包括[!DNL Geography]配置文件）中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。
