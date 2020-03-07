---
description: 趋势线可让您叠加图表，以便比较和解释数据。
title: 趋势线
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 趋势线{#trend-lines}

趋势线可让您叠加图表，以便比较和解释数据。

与[散点图](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-scat-plots.html)可视化类似，您现在可以在图表可视化中设置趋势线，以显示基于线性、指数、幂或多项式线的更改率。趋势线功能允许您在图表上叠加趋势线，通常是在时间维度上叠加。

例如，在本图表比较中，我们可以看到访问次数的趋势向上，而订购的趋势向下。

![](assets/trend_line.png)

如何添加趋势线

1. 打开一个图表，然后右键单击左上角的量度名称。
1. 单击 **[!UICONTROL Trend Lines]** 并从选项中进行选择。

   ![](assets/trend_line_graph.png)

   您可以选择使趋势线叠加在图表上并呈现“简单线性”****、“指数”****、“幂”****&#x200B;或“多项式”****&#x200B;等性质。多项式将创建一个多项式回归趋势线。简单线性将沿着回归线创建一条作为更改率的趋势线。指数将根据 y = b*exp( *x ) 计算趋势线，幂则根据 y = b*x`<sup>a</sup>`a 计算趋势线。

   趋势将在图表中进行计算并呈现，并且在此过程中将会打开一个标注以显示趋势方程的详细信息。

   ![](assets/trend_line_detail.png)

