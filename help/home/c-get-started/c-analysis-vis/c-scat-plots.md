---
description: 散点图用网格绘制数据维度的元素（例如“页面”或“城市”），其中 x 和 y 轴表示不同的量度。
title: 2D 散点图
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
exl-id: 340f8c18-ce47-4f3a-aba4-3d6124505313
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 86%

---

# 2D 散点图{#d-scatter-plots}

散点图用网格绘制数据维度的元素（例如“页面”或“城市”），其中 x 和 y 轴表示不同的量度。

当尝试通过两个不同的量度了解大量不同的项目之间的关系时，散点图可能非常有用。在以下示例中，散点图根据访客数和各自的维系率来显示每个城市。

![](assets/vis_ScatterPlot_City.png)

使用散点图，您可以快速查看异常值。例如，盐湖城每个访客的平均维系率较高。

散点图还可用于显示数据一致性。在以下示例中，散点图显示具有特定长度会话的访客数量。

![](assets/vis_ScatterPlot_SessionDuration.png)

散点图上每个点的大小由半径量度确定。Adobe 应用程序的默认半径量度各不相同。例如，在 [!DNL Site] 中，默认情况下半径量度基于“会话”。可以更改半径量度，以在您的散点图中包含表示任何可用量度的点。有关此操作的步骤，请参阅[更改半径量度](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a)。点的颜色基于工作区中打开的颜色图例。有关颜色图例的详细信息，请参阅[颜色图例](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)。

## 选择点{#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**选择单个点**

* 单击该点。

**向选择中添加另一个点或点组**

* 按 Ctrl 并单击某个点或按 Ctrl 并跨多个点拖动。

**从选择中删除某个点或点组**

* 按 Shift 并单击某个点或按 Shift 并跨多个点拖动。

## 更改维{#section-796cd962ef3f476caa89d99083782ed1}

* 右键单击图形顶部的维度标签，然后单击&#x200B;**[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*。

## 更改量度{#section-44b8be9215cd4039b1eeb98ae1b31445}

**更改散点图的 x 或 y 轴上显示的量度**

* 右键单击要更改的量度的标签，然后单击&#x200B;**[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*。

## 更改半径量度{#section-fd80576d583c430cb469daf12e39aa2a}

**更改散点图的半径量度**

右键单击图形顶部的维度标签，然后单击&#x200B;**[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*。

![](assets/mnu_ScatterPlot_Change.png)
