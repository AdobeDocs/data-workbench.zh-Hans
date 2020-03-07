---
description: 聚类生成器当前包含 KMeans++ 算法（之前仅支持 KMeans 算法），该算法可使用更快的方法找到迅速生成聚类的中心。
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Clustering 2.0{#clustering}

聚类生成器当前包含 KMeans++ 算法（之前仅支持 KMeans 算法），该算法可使用更快的方法找到迅速生成聚类的中心。

## KMeans 算法 {#section-92383a1be1d6402c95a25c902e90b850}

In the [Cluster Builder](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html), you can now select **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** to select algorithms when defining clusters.

* **[!UICONTROL KMeans]**。此算法使用 Canopy 聚类来定义聚类的中心。
* **[!UICONTROL KMeans++]**。此算法可在针对大量数据集运行时加快聚类构建。

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ 是一种改进的 KMeans 聚类算法实施，因为它可以对初始的 k 中心进行更好的初始化。（原始的 KMeans 算法随机选择初始中心。）KMeans++ 随机选择第一个中心。对于其余的 k-1 中心，将根据数据点与最近的现有中心之间的距离，一个个地选择它们。较远的数据点比近处的数据点更有机会被选为新的中心。在选择初始中心后，将执行与原始 KMeans 聚类完全一样的流程。

KMeans++ 的工作流程与 KMeans 聚类的工作流程几乎完全相同，除了需要在聚类生成器中选择&#x200B;**选项** > **算法** > **KMeans++** 之外。

>[!NOTE]
>
>每个DPU在其自己的数据部分上运行自己的KMeans++过程。 如果 DPU 拥有足够的可用内存（其比率可在 PAServer.cfg 文件中配置），则这些相关变量的数据将被导入内存。其余的 k-1 初始中心选择和收敛迭代全部在内存中进行，这比之前的 KMeans 聚类快得多。

