---
description: 弦图可视化允许您同时显示量度之间的比例和关联，从而将较大的弦图显示为一个更强关联的象征。
title: 和弦可视化图表
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
exl-id: d712f7b3-de2f-4ca4-a1bf-a2e4d42a084e
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 85%

---

# 和弦可视化图表{#chord-visualization}

弦图可视化允许您同时显示量度之间的比例和关联，从而将较大的弦图显示为一个更强关联的象征。

弦图可视化可让您确定量度之间的关联，从而能够添加并轻松评估可能的关联。通过它还可以查看之前构建的任何[关联矩阵](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)。使用弦图可视化时，您无法确定量度之间的关联是正还是负，只知道存在这种关联。在某些情况下，可通过应用计数器量度来确定直接或反向关系。

1. **打开可&#x200B;**[!UICONTROL Chord]**视化**。

   在工作区中，右键单击[!DNL Visualization > Predictive Analytics > Chord]。

1. **从菜单中选择一个维度**。

   将会打开一个空白的可视化，供您选择维度。维度名称将显示在空白弦图可视化的顶部。

   >[!NOTE]
   >
   >如果已在工作区中打开关联矩阵，则还可以将其渲染为弦图可视化。

1. **选择要关联的量度**。

   通过单击&#x200B;**[!UICONTROL Ctrl-Alt]**&#x200B;将&#x200B;**[!UICONTROL Finder]**&#x200B;中的量度从表拖到图表中。 在选择两个或更多量度之后，图表将自动刷新并开始显示关联数据。根据需要，继续添加量度以关联数据点。

   ![](assets/chord_drag_metric.png)

   弦图可视化显示由每个区段区域表示的整体比例。根据需要，继续添加量度以识别和调查重要关系。

   ![](assets/chord_selected.png)

1. **查看弦图可视化**。

   将鼠标悬停在可视化中的每个量度上，查看关系。在该示例中，您可以看到件数和其他大部分量度（除了&#x200B;**访问持续时间**&#x200B;量度）之间的关联。

   ![](assets/chord_visualization_1.png)

   将鼠标悬停在弦图可视化中的&#x200B;**访问持续时间**&#x200B;量度上，可以看到所有其他量度之间存在很少或者非常微弱的关联。

   ![](assets/chord_visualization_2.png)

1. **更改设置。**&#x200B;右键单击弦图可视化以打开一个菜单，其中可更改维度、将维度显示为绝对数值或百分比、删除选定量度或全部量度、编辑颜色和详细信息、并将值导出到关联矩阵。

   ![](assets/chord_menu.png)
