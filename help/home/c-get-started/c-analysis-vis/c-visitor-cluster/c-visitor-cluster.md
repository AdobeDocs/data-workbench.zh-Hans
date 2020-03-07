---
description: 通过访客聚类，您可以利用客户特性对访客进行动态分类，并基于选定的数据输入生成聚类集，从而识别具有相似兴趣和行为的群组，以便进行客户分析和定位。
solution: Analytics
title: 访客聚类
topic: Data workbench
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 访客聚类{#visitor-clustering}

通过访客聚类，您可以利用客户特性对访客进行动态分类，并基于选定的数据输入生成聚类集，从而识别具有相似兴趣和行为的群组，以便进行客户分析和定位。

**聚类流程**

聚类流程需要您识别可用作输入的量度和维度元素，并允许您选择一个特定目标人群，以应用这些元素创建指定的聚类。在运行聚类流程时，系统会使用量度和维度输入，为指定数量的聚类确定正确的初始中心。这些中心此后将作为应用 K-Means 算法的起点。

![](assets/K_algorithm.png)

* 通过 Canopy 聚类传递，可智能化地选择初始中心。
* 通过将每个数据点关联到最近的中心，可创建数据聚类。
* 每个 K 聚类的均值将成为新的中心。
* 在步骤 2 和 3 中重复此算法，直到实现聚合为止。这可能需要多次传递。

The **[!UICONTROL Maximum Iterations]** in the **[!UICONTROL Options]** menu allows the analyst to specify the maximum number of iterations to be performed by the clustering algorithm. 设置此选项，可能会以降低聚类中心聚合的准确度为代价，更快地完成基于最大迭代上限的聚类流程。

>[!NOTE]
>
>定义群集后，可以保存群集维以便像任何其他维一样使用。 也可以将它加载到聚类浏览器中，以检查聚类中心的分离情况。

In the Cluster Builder, you can select **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** to select algorithms when defining clusters. 目前，有3种支持的算法：

* KMeans
* Kmeans`++`
* 期望最大化

有两种方法可运行群集过程：

* 方法1 —— 在群集 **[!UICONTROL Go]** 可视化窗口中单击。
* 方法2 —— 在群集 **[!UICONTROL Submit]** 可视化窗口中单击，该窗口将群集作业直接发送到服务器。 您可以通过“查询的详细状态”选项跟踪进度。

![](assets/dwb_visitorclustering.png)

该算法具有以下限制：

1. 如果您使用方法1，则可以选择任何支持的聚类算法。
1. 如果您使用方法2，则可以选择kmeans或kmeans++。 “期望最大化”(Expectation Maximization)选项将不可用。

>[!NOTE]
>
>在文 [!DNL DPU.cfg] 件中，“查询，内存限制”的值默认设置为500 MB。 运行多个群集作业时必须增加此值。 例如，如果您并行运行5个群集作业，请将此值增加到1 GB。 如果不重新启动服务器，就无法取消群集作业。

**推荐**

迭代次数（扫描数据的次数）和您配置的收敛阈值会严重影响群集性能。 下表提供了更广泛的指导原则，您可以遵循这些原则：

| 群集数 | 算法 | 迭代 | 收敛阈值 | 标准化 |
|---|---|---|---|---|
| 6 | Kmeans | 25,50 | 1e-3 | 最小——最大 |
| 6 | Kmeans | 25,50 | 1e-6 | 最小——最大 |
| 6 | Kmeans++ | 50 | 1e-6 | 最小——最大 |
