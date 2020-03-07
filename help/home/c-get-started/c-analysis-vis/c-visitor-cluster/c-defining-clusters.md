---
description: 选择输入变量、聚类数量以及目标人群（如果需要），以便定义数据集中的聚类。
solution: Analytics
title: 构建聚类
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 构建聚类{#building-clusters}

选择输入变量、聚类数量以及目标人群（如果需要），以便定义数据集中的聚类。

**构建聚类**

1. 打开 **[!UICONTROL Cluster Builder]**.

   单击&#x200B;**可视化** > **预测分析** > **聚类** > **聚类生成器**。

   ![](assets/cluster-builder-step1.png)

1. 选择输入变量。

   * Add metrics to the **[!UICONTROL Input Variables]** list by selecting from the **[!UICONTROL Metric]** menu in the toolbar.

      ![](assets/cluster_metric_select.png)

   * Add dimension elements to the **[!UICONTROL Input Variables]** list by dragging them from a Dimension&#39;s table.

      Press **[!UICONTROL Ctrl + Alt]** and drag selected dimension elements to the **[!UICONTROL Input Variables]** list or to the **[!UICONTROL Element]** box in the toolbar.

      ![](assets/cluster_dim_select.png)
   默认情况下，聚类会在整个数据集上执行。You can see all input variables in the left **[!UICONTROL Preprocessing]** pane.
1. Use the **[!UICONTROL Options]** menu to select the desired number of clusters.

   ![](assets/build_cluster_2.png)

1. 如果您要在数据集中聚集访客数的子集，则可以定义人群过滤器。

   ![](assets/build_cluster_3.png)

   Start by defining the desired subset using selections in your Workspace or by using the **[!UICONTROL Filter Editor]**. Once you have the desired subset selected, set the Target Population in the **[!UICONTROL Options]** menu. 建议您为目标群组提供一个标识名称。

   The **[!UICONTROL Options]** menu also has settings to control the maximum number of passes and the acceptable threshold for center convergence.

1. After inputs and options have been configured, click the **Go** button to run the clustering locally or press **[!UICONTROL Submit]** to send the task to the Predictive Analytics Server. 收敛完成时，提交到服务器的任务会将结果维度保存到数据集。

   当在本地运行时，您将看到聚类生成器会随其根据输入定义智能中心，在四个 Canopy 聚类阶段之间移动。

   当聚类中心停止更改超过指定的收敛阈值时，聚类维度会被收敛，并且聚类生成器将显示有关输入与每个聚类相关程度的额外信息。

1. 自定义聚类。

   右键单击统计信息的颜色条可打开一个上下文菜单，该菜单允许您自定义相关性阈值，并且对于维度元素分配，还允许选择要显示的测试。

   ![](assets/build_cluster_7.png)

   量度输入为每个聚类提供一个 T 检定，而维度元素输入为每个聚类提供三个分配测试（卡方、熵 U 统计及 Cramer&#39;s V 统计）。

   >[!NOTE]
   >
   >If you add or remove inputs during convergence, the process will pause until you press **Go** again.

   构建聚类后，您可以打开拾色器为不同的分配结果指定颜色。

   ![](assets/build_cluster_5.png)

1. 聚类维度收敛后，您可以将量度添加到表格中，并像往常一样做出选择。您还可以右键单击元素名称（聚类 1、聚类 2 等）来打开上下文菜单，将这些元素重命名为更有意义的名称。

   ![](assets/build_cluster_6.png)

1. If you wish to use this cluster dimension in other visualizations, you can **[!UICONTROL Save]** it locally or **[!UICONTROL Submit]** it to the server.

如果您希望再次运行收敛或查看输入的相关性，聚类生成器也可以加载现有的聚类维度。

>[!TIP]
>
>When selected, **[!UICONTROL Reset]** will completely release all the input variables and give you a blank cluster builder visualization to define new clusters.

