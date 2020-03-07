---
description: 如果您订阅了任一数据服务，则必须定期更新Adobe提供的数据服务文件。
solution: Analytics
title: 更新数据服务文件
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 更新数据服务文件{#updating-data-service-files}

如果您订阅了任一数据服务，则必须定期更新Adobe提供的数据服务文件。

为此，您必须有权访问Data Workbench Server上的文件。

要加载或 [!DNL IP Geo-location] 数据 [!DNL IP Geo-intelligence] 文件，您必须完成以下过程。

## 替换数据文件 {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在Data Workbench中，在 [!DNL Admin] >选 [!DNL Dataset and Profile] 项卡上，单击缩 **[!UICONTROL Servers Manager]** 略图以打开工作 [!DNL Servers Manager] 区。

1. 在窗 [!DNL Servers Manager] 口中，右键单击要将文件加载到的Data Workbench Server图标，然后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]在列中单击或，然后 **[!UICONTROL Temp]** 单 **[!UICONTROL Lookups\IP Geo-location]** 击> **[!UICONTROL Lookups\IP Geo-intelligence]** &lt; **[!UICONTROL Open]*****[!UICONTROL folder]***>右键。

1. 将Adobe [!DNL .bin] 提供的数据文件复制到“Lookups\IP Geo-location”或“Lookups\IP Geo-intelligence”文件夹窗口。
1. 将文件保存到Data Workbench Server计算机，方法是右键单击数据文 [!DNL Temp] 件的列，然后单击 **[!UICONTROL Save to]** > *&lt;&lt;**[!UICONTROL server name]**>*。

   如果运行的是群集，则将文件上传到群集中的主Data Workbench Server。

## 更新IPLookup转换 {#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在中， [!DNL Profile Manager]单击 **[!UICONTROL Dataset]**、 **[!UICONTROL Transformation]**&#x200B;和 **[!UICONTROL Geography]**。

1. 右键单击旁边的复选标记， [!DNL IP Lookup.cfg] 然后单击 **[!UICONTROL Make Local]**。 A check mark for this file appears in the [!DNL User] column.

1. 右键单击新复选标记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现转换配置窗口。

1. 在窗口中，单击， **[!UICONTROL Transformation]**&#x200B;然后单击 **[!UICONTROL Transformations]**。

1. 找到并单击或 **[!UICONTROL IPLookup Quova]** 中的任一 **[!UICONTROL IPLookup Digital Envoy]**&#x200B;项。

1. 对于“文件”参数，请更新文件的名称以与Adobe提供的新数据( [!DNL .bin])文件的名称匹配。
1. 通过右键单击配置窗口顶部的 **[!UICONTROL (modified)]** 并单击，保存转换配置文件 **[!UICONTROL Save]**。

1. 将修改后的配置文件保存到使用数据服务的每个配置文件中，方法是右键单击列中 [!DNL IP Lookup.cfg] 旁边的复 [!DNL User] 选标记，然后单 **[!UICONTROL Save to]** 击> *&lt;**[!UICONTROL profile name]**>*。 在数据集配置文件同步之后，系统便会开始重新转换数据。

   有关重新转换数据集的信息，请参阅《数据集配置指南》的“重新处理和重新转 *换”一章*。

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] profile), as your changes are overwritten when you install updates to these profiles.

如果您为5. [!DNL IP Geo-intelligence] 1版或 [!DNL IP Geo-location] 更高版本安装了和数据服务，则您已完成数据服务更新。 但是，如果您在5.1 [!DNL IP Geo-intelligence] 版之 [!DNL IP Geo-location] 前安装了和数据服务，则必须完成以下附加步骤。

## 替换查找文件 {#section-ced1efa38a76419d812edd35423dbff7}

只有在5.1版之前安装了和数 [!DNL IP Geo-intelligence] 据服务 [!DNL IP Geo-location] 时，才应完成以下步骤。

1. 在中，单 [!DNL Server Files Manager]击> **[!UICONTROL Profiles]** 或 **[!UICONTROL IP Geo-intelligence]** > **[!UICONTROL Profiles]** ，然 **[!UICONTROL IP Geo-location]**&#x200B;后单击 **[!UICONTROL Maps]** 查看其内容。

1. 右键单击列 **[!UICONTROL Temp]** ，然后 **[!UICONTROL Maps]** 单击 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*。

1. 将Adobe提供 [!DNL .txt] 的新文件复制到“地图”文件夹窗口。
1. 将文件保存到Data Workbench Server计算机，方法是右键单击文件列中的复选 [!DNL Temp] 标记，然 [!DNL .txt] 后单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

>[!NOTE]
>
>如果运行的是群集，则将文件上传到群集中的主Data Workbench Server。

## 更新图层文件 {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>只有在5.1版之前安装了和数 [!DNL IP Geo-intelligence] 据服务 [!DNL IP Geo-location] 时，才应完成以下步骤。

为引用或查找()文 [!DNL .layer]件的每个层()文 [!DNL IP Geo-intelligence] 件完 [!DNL IP Geo-location] 成这些 [!DNL .txt]步骤。

1. 在Data Workbench Server安装目录的Profiles\*data service name*\Maps文件夹中，在文本编辑器（如记事本） [!DNL .layer] 中打开该文件。

1. 在矢量 [!DNL Data Paths] 中，更新查找文件的名称以与Adobe提供的新文件的名 [!DNL .txt][!DNL .txt] 称相匹配，如以下文件示例中所示：

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
1. 对于引用该或文件的每 [!DNL .layer] 个文件，重复步骤2 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location][!DNL .txt] 3。

