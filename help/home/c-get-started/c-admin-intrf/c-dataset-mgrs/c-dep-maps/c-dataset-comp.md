---
description: 有关数据集组件的概念性信息。
title: 数据集组件
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 57%

---

# 数据集组件{#dataset-components}

有关数据集组件的概念性信息。

下图显示了一幅依赖关系图，其中的节点表示数据集的日志源、字段、转换和扩展维度。

![](assets/vis_DependencyMap.png)

* 黄绿色节点表示在数据集中定义的一个或多个日志源或过滤器（如日志条目条件）。

   * 日志源的节点始终显示在图中的最左侧。如果您的数据集只有一个日志源，则图中会显示“日志源: *日志源名称*”。如果您的数据集有多个日志源，则图中会显示“*数字*&#x200B;个数据源”，其中的“数字”是日志源的计数。例如，如果您的数据集有三个日志源，则图中会显示“3 个日志源”。

   * 该映射为每个[!DNL log processing dataset include]文件显示一个“日志条目条件”节点，但只显示一个用于转换的“日志条目条件”节点（如果在[!DNL Transformation.cfg]文件中定义）。 如果日志条目条件为空，则不会显示图中。

* 灰色节点表示在[!DNL Log Processing.cfg]或[!DNL Log Processing include]文件的“字段”参数中列出的字段。

* 蓝色节点表示转换。
* 绿色节点表示扩展维度。

>[!NOTE]
>
>如果用户档案的Dataset文件夹包含文件[!DNL Insight Transform.cfg]，则依赖关系图将显示为与转换一起使用而定义的日志源、转换和导出器。 有关转换的信息，请参阅《数据集配置指南》**。

启用“包含[!DNL File Blocks]”显示选项后，映射将显示一个蓝色节点用于一个数据集配置文件中定义的所有转换，一个绿色节点用于一个数据集配置文件中定义的所有扩展维度。 有关此显示选项的详细信息，请参阅[使用文件块](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)。
