---
description: 有关数据集组件的概念性信息。
title: 数据集组件
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 57%

---

# 数据集组件{#dataset-components}

{{eol}}

有关数据集组件的概念性信息。

下图显示了一幅依赖关系图，其中的节点表示数据集的日志源、字段、转换和扩展维度。

![](assets/vis_DependencyMap.png)

* 黄绿色节点表示在数据集中定义的一个或多个日志源或过滤器（如日志条目条件）。

   * 日志源的节点始终显示在图中的最左侧。如果您的数据集只有一个日志源，则图中会显示“日志源: *日志源名称*”。如果您的数据集有多个日志源，则图中会显示“*数字*&#x200B;个数据源”，其中的“数字”是日志源的计数。例如，如果您的数据集有三个日志源，则图中会显示“3 个日志源”。

   * 该映射为每个日志条目条件显示一个节点 [!DNL log processing dataset include] 文件，但只有一个用于转换的日志条目条件节点(如果在 [!DNL Transformation.cfg] 文件)。 如果日志条目条件为空，则不会显示图中。

* 灰色节点表示在 [!DNL Log Processing.cfg] 或 [!DNL Log Processing include] 文件。

* 蓝色节点表示转换。
* 绿色节点表示扩展维度。

>[!NOTE]
>
>如果您配置文件的Dataset文件夹包含该文件 [!DNL Insight Transform.cfg]，依赖关系图会显示为与转换一起使用而定义的日志源、转换和导出程序。 有关转换的信息，请参阅《数据集配置指南》**。

启用“Include（包含）”时 [!DNL File Blocks] 显示选项时，映射会显示一个蓝色节点（用于一个数据集配置文件中定义的所有转换）和一个绿色节点（用于一个数据集配置文件中定义的所有扩展维度）。 有关此显示选项的更多信息，请参阅 [使用文件块](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
