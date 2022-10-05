---
description: 如果您订阅任一数据服务，则必须定期更新由Adobe提供的数据服务文件。
title: 更新数据服务文件
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---

# 更新数据服务文件{#updating-data-service-files}

{{eol}}

如果您订阅任一数据服务，则必须定期更新由Adobe提供的数据服务文件。

要执行此操作，您必须有权访问Data Workbench Server上的文件。

加载 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 数据文件时，必须完成以下过程。

## 替换数据文件 {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在Data Workbench中， [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开 [!DNL Servers Manager] 工作区。

1. 在 [!DNL Servers Manager] 窗口中，右键单击要将文件加载到的Data Workbench Server图标，然后单击 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，右键单击 **[!UICONTROL Temp]** 列 **[!UICONTROL Lookups\IP Geo-location]** 或 **[!UICONTROL Lookups\IP Geo-intelligence]** 单击 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. 复制 [!DNL .bin] 由Adobe提供到Lookups\IP Geo-location或Lookups\IP Geo-intelligence文件夹窗口的数据文件。
1. 通过右键单击 [!DNL Temp] 列，并单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   如果您正在运行群集，请将文件上载到群集中的主控Data Workbench Server。

## 更新IPLookup转换 {#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在 [!DNL Profile Manager]，单击 **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]**&#x200B;和 **[!UICONTROL Geography]**.

1. 右键单击旁边的复选标记 [!DNL IP Lookup.cfg] 单击 **[!UICONTROL Make Local]**. 此文件的复选标记将显示在 [!DNL User] 列。

1. 右键单击新复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 出现转换配置窗口。

1. 在窗口中，单击 **[!UICONTROL Transformation]**，然后单击 **[!UICONTROL Transformations]**.

1. 找到并单击 **[!UICONTROL IPLookup Quova]** 或 **[!UICONTROL IPLookup Digital Envoy]**.

1. 对于File（文件）参数，更新文件的名称以匹配新数据的名称( [!DNL .bin])文件。
1. 通过右键单击保存转换配置文件 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

1. 通过右键单击旁边的复选标记，将修改的配置文件保存到使用数据服务的每个配置文件中 [!DNL IP Lookup.cfg] 在 [!DNL User] 列，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. 在数据集配置文件同步之后，系统便会开始重新转换数据。

   有关数据集重新转换的信息，请参阅 *数据集配置指南*.

   >[!NOTE]
   >
   >请勿将修改的配置文件保存到由Adobe提供的任何内部配置文件(包括 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 配置文件)，因为您在安装这些配置文件的更新时，所做的更改会被覆盖。

如果您安装了 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 数据服务版本5.1或更高版本时，您已完成数据服务更新。 但是，如果您安装了 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 数据服务在版本5.1之前，您必须完成以下其他过程。

## 替换对照文件 {#section-ced1efa38a76419d812edd35423dbff7}

仅当安装了 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 数据服务版本5.1之前的版本。

1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** 或 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**，然后单击 **[!UICONTROL Maps]** 查看其内容。

1. 在 **[!UICONTROL Temp]** 列 **[!UICONTROL Maps]** 单击 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. 复制新 [!DNL .txt] 文件(由Adobe提供)。
1. 右键单击 [!DNL Temp] 列 [!DNL .txt] 文件，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>如果您正在运行群集，请将文件上载到群集中的主控Data Workbench Server。

## 更新层文件 {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>仅当安装了 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 数据服务版本5.1之前的版本。

完成每个层的这些步骤( [!DNL .layer])文件 [!DNL IP Geo-intelligence] 或 [!DNL IP Geo-location] 对照( [!DNL .txt])文件。

1. 在Data Workbench Server安装目录的Profiles\*data Service Name*\Maps文件夹中，打开 [!DNL .layer] 文件（如记事本）。

1. 在 [!DNL Data Paths] 矢量，更新 [!DNL .txt] 用于匹配新 [!DNL .txt] 文件，如以下文件示例中突出显示的Adobe提供：

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. 保存更新的层文件。
1. 对每个 [!DNL .layer] 引用的文件 [!DNL IP Geo-intelligence] 或 [!DNL IP Geo-location] [!DNL .txt] 文件。
