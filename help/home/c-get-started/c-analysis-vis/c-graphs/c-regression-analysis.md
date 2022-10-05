---
description: Data Workbench 中的条形图当前可在多个图表之间对多个量度进行回归比较。
title: 回归分析图
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
exl-id: bfc76c4a-edd5-41fe-b875-c199ea3beab5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 94%

---

# 回归分析图{#regression-analysis-graph}

{{eol}}

Data Workbench 中的条形图当前可在多个图表之间对多个量度进行回归比较。

Data Workbench 中的[条形图](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html)可让您将一个图表中的量度回归到另一个图表中的量度。如果您有多个图表，则可以将一个量度（作为自变量）与评估其他量度（作为因变量）的图表进行比较。这可让您确定一个因变量（最先确立的量度）与一系列其他变化量度（具有已确立的依赖量度的回归）之间的关系强度。

图表可视化中的回归分析允许分析人员执行“假设”场景。例如，如果访问次数增加到此级别，这种增长会对收入造成何种影响？

**设置回归分析**

1. 选择图表作为依赖量度，以便进行回归比较。

   右键单击此图表并选择&#x200B;**设置为回归的基本量度**。

   ![](assets/c_graph_regression_1.png)

1. 将其他量度图表设置为自变量。

   右键单击量度并选择 **[!UICONTROL Regress with `<base metric name>`]** 的其他量度。

   ![](assets/c_graph_regression.png)

1. 通过右键单击图表以上下移动条形图的方式查看回归。

   右键单击对应某特定值的图表，可看到基于每个量度的回归比率，以上升或下降的值表示。

   ![](assets/c_graph_regression_2.png)

   例如，如果我的页面查看次数下降到 86,041，则其他量度将具有以下值：访问次数为 12,183、基于访问的访客数为 12,028。

   ![](assets/c_graph_regression_3.png)

   如果基于访问的访客数上升到 26,141，则其他量度将具有以下值：访问次数为 26,560，页面查看次数为 189,091。
