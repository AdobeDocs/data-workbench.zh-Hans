---
description: 如果您订阅了任一数据服务，则必须定期更新由Adobe提供的数据服务文件。
title: 更新数据服务文件
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---

# 更新数据服务文件{#updating-data-service-files}

如果您订阅了任一数据服务，则必须定期更新由Adobe提供的数据服务文件。

要执行此操作，您必须有权访问Data Workbench Server上的文件。

要加载[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]数据文件，必须完成以下过程。

## 替换数据文件{#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在Data Workbench的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开[!DNL Servers Manager]工作区。

1. 在[!DNL Servers Manager]窗口中，右键单击要将文件加载到其中的Data Workbench Server的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，右键单击&#x200B;**[!UICONTROL Lookups\IP Geo-location]**&#x200B;或&#x200B;**[!UICONTROL Lookups\IP Geo-intelligence]**&#x200B;的&#x200B;**[!UICONTROL Temp]**&#x200B;列，然后单击&#x200B;**[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*。

1. 将Adobe提供的[!DNL .bin]数据文件复制到“Lookups\IP Geo-location”（查找\IP地理位置）或“Lookups\IP Geo-intelligence”（查找\IP Geo-intelligence）文件夹窗口。
1. 右键单击数据文件的[!DNL Temp]列，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*，将文件保存到Data Workbench Server计算机。

   如果运行的是群集，请将文件上传到群集中的主控Data Workbench Server。

## 更新IPLookup转换{#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Dataset]**、**[!UICONTROL Transformation]**&#x200B;和&#x200B;**[!UICONTROL Geography]**。

1. 右键单击[!DNL IP Lookup.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 此文件的复选标记显示在[!DNL User]列中。

1. 右键单击新复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出现转换配置窗口。

1. 在窗口中，单击&#x200B;**[!UICONTROL Transformation]**，然后单击&#x200B;**[!UICONTROL Transformations]**。

1. 找到并单击&#x200B;**[!UICONTROL IPLookup Quova]**&#x200B;或&#x200B;**[!UICONTROL IPLookup Digital Envoy]**。

1. 对于File参数，请更新文件的名称以与Adobe提供的新数据([!DNL .bin])文件的名称匹配。
1. 通过右键单击配置窗口顶部的&#x200B;**[!UICONTROL (modified)]**&#x200B;并单击&#x200B;**[!UICONTROL Save]**&#x200B;保存转换配置文件。

1. 将修改后的配置文件保存到使用数据服务的每个用户档案，方法是右键单击[!DNL User]列中[!DNL IP Lookup.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。 在数据集配置文件同步之后，系统便会开始重新转换数据。

   有关重新转换数据集的信息，请参阅&#x200B;*Dataset Configuration Guide*&#x200B;的Reprocessing and Retransformation一章。

   >[!NOTE]
   >
   >请勿将修改后的配置文件保存到Adobe提供的任何内部用户档案(包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]用户档案)，因为当您安装这些用户档案的更新时，您所做的更改会被覆盖。

如果您为版本5.1或更高版本安装了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]数据服务，则您已完成数据服务更新。 但是，如果您在5.1版之前安装了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]数据服务，则必须完成以下附加过程。

## 替换查找文件{#section-ced1efa38a76419d812edd35423dbff7}

只有在5.1之前安装了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]数据服务时，才应完成以下步骤。

1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]**&#x200B;或&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]** ，然后单击&#x200B;**[!UICONTROL Maps]**&#x200B;视图其内容。

1. 右键单击&#x200B;**[!UICONTROL Maps]**&#x200B;的&#x200B;**[!UICONTROL Temp]**&#x200B;列，然后单击&#x200B;**[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*。

1. 将Adobe提供的新[!DNL .txt]文件复制到Maps文件夹窗口。
1. 右键单击[!DNL .txt]文件[!DNL Temp]列中的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*，将文件保存到Data Workbench Server计算机。

>[!NOTE]
>
>如果运行的是群集，请将文件上传到群集中的主控Data Workbench Server。

## 更新图层文件{#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>只有在5.1之前安装了[!DNL IP Geo-intelligence]和[!DNL IP Geo-location]数据服务时，才应完成以下步骤。

完成引用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]查找([!DNL .txt])文件的每个图层([!DNL .layer])文件的这些步骤。

1. 在Data Workbench Server安装目录中的“用户档案”\*数据服务名称*\Maps文件夹中，在文本编辑器（如记事本）中打开[!DNL .layer]文件。

1. 在[!DNL Data Paths]矢量中，更新[!DNL .txt]查找文件的名称以与Adobe提供的新[!DNL .txt]文件的名称匹配，如以下文件示例中突出显示：

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

1. 保存更新的图层文件。
1. 对每个引用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location] [!DNL .txt]文件的[!DNL .layer]文件重复步骤2和步骤3。
