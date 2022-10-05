---
description: 可以将流程图配置为使用基本维度、组维度、级别维度和对应用程序和数据集有益的量度的组合。
title: 配置流程图
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 63%

---

# 配置流程图{#configure-a-process-map}

{{eol}}

可以将流程图配置为使用基本维度、组维度、级别维度和对应用程序和数据集有益的量度的组合。

配置流程图后，它将与 [!DNL Add Visualization menu].

1. 在 [!DNL Profile Manager]，单击 **[!UICONTROL Menu]**，单击 **[!UICONTROL Add Visualization]**，然后单击要配置的流程图类型（“2D量度图”、“2D流程图”或“3D流程图”）。

   至少一个 [!DNL *.vw] 文件位于目录中。

1. 右键单击所需文件的复选标记，然后单击 **[!UICONTROL Make Local]**.
1. 右键单击 [!DNL User] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 参考以下示例文件和表格，编辑文件的参数：

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 对于该参数... </th> 
   <th colname="col2" class="entry"> 提供此信息... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Metric name（量度名称）</i> </p> </td> 
   <td colname="col2"> <p>量度的名称，此量度指定节点的值与节点的大小成正比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Base dimension name（基本维度名称）</i> </p> </td> 
   <td colname="col2"> <p>元素在流程图上显示为节点的维度的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Level dimension name（级别维度名称）</i> </p> </td> 
   <td colname="col2"> <p>将其元素拖动到流程图的基本维度的级别（父级）名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Group dimension name（组维度名称）</i> </p> </td> 
   <td colname="col2"> <p>维度的名称，此维度用于确定如何组合级别维度的元素以在节点之间形成连接。两个节点之间的连接不能跨越组维度的多个元素。当您在流程图中根据节点做出选择时，即选择了包含该节点的组维度的所有元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Metric name for metric map（量度图的量度名称）</i> </p> </td> 
   <td colname="col2"> <p>此参数仅适用于 2D 量度图。 </p> <p>量度的名称，此量度的值用来确定图上节点的水平位置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有关流程图的基本维度、组维度、级别维度和量度的更多信息，请参阅 [流程图](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. 在记事本中，单击 **[!UICONTROL File]** > **[!UICONTROL Save As]** 使用基本维度(即， *基本维度名称*.vw.

   （如果您配置的是 2D 量度图，则应使用基于量度图量度名称的名称（即&#x200B;*量度图的量度名称*.vw）保存文件。）确保您将文件保存到相应的流程图目录。

   >[!NOTE]
   >
   >确保将流程图另存为 [!DNL *.vw] 文件，在 [!DNL Save As] ，请将“另存为”类型设置为“所有文件”。

1. （可选）要使更改对工作配置文件的所有用户可用，请在 [!DNL Profile Manager]，右键单击 [!DNL User] 列，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
