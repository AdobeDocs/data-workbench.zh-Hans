---
description: 有关数据集组件的概念性信息。
solution: Analytics
title: 数据集组件
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dataset components{#dataset-components}

有关数据集组件的概念性信息。

下图显示了一幅依赖关系图，其中的节点表示数据集的日志源、字段、转换和扩展维度。

![](assets/vis_DependencyMap.png)

* 黄绿色节点表示在数据集中定义的一个或多个日志源或过滤器（如日志条目条件）。

   * 日志源的节点始终显示在图中的最左侧。如果您的数据集只有一个日志源，则图中会显示“日志源: *日志源名称*”。如果您的数据集有多个日志源，则图中会显示“*数字*&#x200B;个数据源”，其中的“数字”是日志源的计数。例如，如果您的数据集有三个日志源，则图中会显示“3 个日志源”。

   * The map displays one Log Entry Condition node for each [!DNL log processing dataset include] file but only one Log Entry Condition node for transformation (if defined in the [!DNL Transformation.cfg] file). 如果日志条目条件为空，则不会显示图中。

* A gray node represents a field that is listed in the Fields parameter in a [!DNL Log Processing.cfg] or [!DNL Log Processing include] file.

* 蓝色节点表示转换。
* 绿色节点表示扩展维度。

>[!NOTE]
>
>If your profile’s Dataset folder contains the file [!DNL Insight Transform.cfg], the dependency map shows the log sources, transformations, and exporters defined for use with Transform. 有关转换的信息，请参阅《数据集配置指南》**。

When you enable the Include [!DNL File Blocks] display option, the map displays a single blue node for all of the transformations defined in one dataset configuration file and a single green node for all of the extended dimensions defined in one dataset configuration file. 有关此显示选项的详细信息，请参阅 [使用文件块](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)。
