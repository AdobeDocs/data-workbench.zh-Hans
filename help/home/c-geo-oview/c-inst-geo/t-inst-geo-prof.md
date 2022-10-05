---
description: 随Data WorkbenchGeography一起提供的地理位置配置文件是一个内部配置文件，可为您的Adobe应用程序提供附加功能。
title: 安装地理位置配置文件
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 6%

---

# 安装地理位置配置文件{#installing-the-geography-profile}

{{eol}}

随Data WorkbenchGeography一起提供的地理位置配置文件是一个内部配置文件，可为您的Adobe应用程序提供附加功能。

与Adobe提供的所有其他内部用户档案一样， [!DNL Geography] 配置文件不应更改。 所有自定义都必须在数据集配置文件、特定于角色的配置文件或您创建的其他配置文件中进行。

的 [!DNL Geography] 配置文件包含多个转换数据集包含文件(位于 [!DNL Dataset\Transformation\Geography] 文件夹)。 以下是随 [!DNL Geography] 用户档案：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每个文件都针对它定义的扩展维度进行命名。 另一个文件， [!DNL IPLookup.cfg]，定义多个地理数据字段，这些字段用于定义其他转换数据集包含文件中的维度。

有关转换数据集包含文件的信息，请参阅 *数据集配置指南*.

**安装 [!DNL Geography] data workbench server上的配置文件**

>[!NOTE]
>
>以下安装说明假定您已安装Data Workbench，并在Data Workbench与要安装Data Workbench的Data Workbench Server之间建立了连接 [!DNL Geography]. 如果您尚未执行此操作，请参阅 *Data Workbench用户指南*.

1. 从 [!DNL .zip] 文件(由Adobe提供)。
1. 复制 [!DNL Geography] 文件夹到Data Workbench Server安装目录的Profiles文件夹中。 你最后想用 [!DNL ...\Profiles\Geography] 文件夹，如以下示例中所示。 Profiles文件夹中其他文件夹的名称可能与显示的名称不同。

   ![步骤信息](assets/Geo_installProfiles_dir.png)

1. 请按照以下步骤更新 [!DNL profile.cfg] 文件，以查找要使用data workbench的每个配置文件 [!DNL Geography].

   1. 打开 [!DNL Profile Manager].
   1. 右键单击旁边的复选标记 [!DNL profile.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。

   1. 右键单击新创建的复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 的 [!DNL profile.cfg] 窗口。

   1. 在 [!DNL profile.cfg] 窗口，右键单击 **[!UICONTROL Directories]** 单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      要将新目录添加到目录列表末尾，请右键单击列表中最后一个目录的编号或名称，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 键入新目录的名称： [!DNL Geography].
   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，右键单击的复选标记 [!DNL profile.cfg] 在 [!DNL User] 列，然后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >请勿将修改的配置文件保存到由Adobe提供的任何内部配置文件(包括 [!DNL Geography] 配置文件)，因为您在安装这些配置文件的更新时，所做的更改会被覆盖。
