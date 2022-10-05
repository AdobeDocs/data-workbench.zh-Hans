---
description: 关联弦图可视化允许您同时显示量度、维度和元素之间的比例和关联，从而将较大的弦图显示为一个更强关联的指征。
title: 关联和弦可视化图表
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
exl-id: e71394ef-4895-4a3e-912d-d6f56ca8f001
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 87%

---

# 关联和弦可视化图表{#association-chord-visualization}

{{eol}}

关联弦图可视化允许您同时显示量度、维度和元素之间的比例和关联，从而将较大的弦图显示为一个更强关联的指征。

关联表格将值与 Cramer&#39;s V 计算结果相对比，而非使用[关联矩阵](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md)和[关联弦图](/help/home/c-get-started/c-analysis-vis/associations-visualization.md)可视化中采用的皮尔逊关联系数（关联矩阵和关联弦图只能对比量度，而关联表格和弦图可以对比量度、维度和元素）。关联弦图还可以提供另外一种视图来查看之前构建的[关联表格](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f)。

**构建关联弦图的步骤**

1. 在工作区中，依次右键单击&#x200B;**可视化 > 预测分析 > 关联弦图**。

   接着会打开一个菜单，允许您从列表中选择一个扩展维度。

   ![](assets/association_chord1.png)

   选择完毕后，会打开空白的关联表格，选择的维度会在标题中标出。 ![](assets/association_chord2.png)

1. **选择量度、维度或维度元素**.

   右键单击弦图可视化并选择&#x200B;**添加量度**&#x200B;或&#x200B;**添加维度**。从菜单中选择项目并添加到弦图中。

   您还可以从 **[!UICONTROL Finder]** 单击 **[!UICONTROL Ctrl-Alt]** 和将量度和维度拖到弦图中。 或者从一个打开的表格，直接将维度元素拖放到弦图可视化中。

1. **选择其他量度、维度和元素进行关联**。

   选择两个或更多值之后，图表将自动刷新并开始显示关联数据。根据需要继续添加量度，以关联数据点。

   ![](assets/association_chord.png)

   弦图可视化显示由每个区段区域表示的整体比例。根据需要继续添加量度/维度/元素，以识别和调查重要关系。

1. **查看弦图可视化**。

   将鼠标悬停在可视化中的每个值上，可查看关系。

1. **更改设置。**&#x200B;右键单击弦图可视化可打开菜单，其中可更改量度、维度或元素，可将维度显示为绝对值或百分比，可删除选定量度或所有量度，可编辑颜色和详细信息，还可以将值导出到关联表格。

**从关联表格构建关联弦图的步骤：**

1. 打开&#x200B;**关联表格**&#x200B;可视化。
1. 右键单击并选择&#x200B;**导出弦图可视化**。接着会打开一个关联弦图图表，其中有从关联表格中选择的值。 ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>从至少包含一个量度的关联弦图图中导出关联表格时，将导致关联表格的行/列中出现重复元素。 要避免出现重复元素，请创建新的关联表格并添加所需元素，而不是从关联弦图图表中导出元素。
