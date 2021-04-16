---
description: 通过依赖关系图，可以可视化和管理配置文件组件的配置。
title: 依赖关系图
uuid: c869267c-5fa9-43b8-b4d4-06c7a36bfa8e
exl-id: 4618c735-f507-4abc-a4b4-d52a37c64c60,733407ca-3326-406a-a642-a3ea3d3f6b8b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 87%

---

# 依赖关系图{#dependency-maps}

通过依赖关系图，可以可视化和管理配置文件组件的配置。

* **数据集组** 件：在数据集、文件和文件中定义的日志源、过滤器、字段、转 [!DNL Log Processing.cfg]换 [!DNL Transformation.cfg]和扩展 [!DNL dataset include] 维度。

* **查询模型组件：**&#x200B;在 Dimensions、Metrics 和 Filters 文件夹中定义的维度、量度和过滤器。
* **工作区和可视化：**&#x200B;工作区、报表、菜单选项和全局层。

有关在依赖关系图中处理查询模型组件、工作区和可视化的详细信息，请参阅《Data Workbench 用户指南》**。

配置文件组件在图中由彩色圆点（节点）表示。连接节点的直线描绘了依赖关系，即组件之间是如何彼此关联的。两个节点之间的直线表示左侧节点的输出是右侧节点的输入，即右侧节点依赖于左侧节点。

## 显示数据集组件  {#section-3e51c09c23cc40aeade2e6ad0fa7c8d2}

1. 在依赖关系图中右键单击，然后单击&#x200B;**[!UICONTROL Display]**。
1. 选择 **[!UICONTROL Dataset]**. [!DNL Dataset]的左侧显示X。

有关其他显示选项的详细信息，请参阅《Data Workbench 用户指南》**。

下图显示了一份依赖关系图，其中的节点表示数据集的日志源、字段、转换和扩展维度。

![](assets/vis_DependencyMap.png)

* 黄绿色节点表示数据集中定义的一个或多个日志源或过滤器。日志源的节点始终显示在图中的最左侧。
* 灰色节点表示在[!DNL Log Processing.cfg]或[!DNL Log Processing Include]文件的“字段”参数中列出的字段。

* 蓝色节点表示转换。
* 绿色节点表示扩展维度。

>[!NOTE]
>
>如果您的数据集只有一个日志源，则图中会显示“日志源: *日志源名称*”。如果您的数据集有多个日志源，则图中会显示“*数字*&#x200B;个数据源”，其中的“数字”是日志源的计数。例如，如果您的数据集中有三个日志源，则图中会显示“3 个日志源”。

如果您无法看到图上的所有节点，则可以移动或缩放该图以显示整张图，或重点显示图上某一特定区域。有关缩放操作的详细信息，请参阅《Data Workbench 用户指南》**&#x200B;的“使用可视化”一章。

在单击某个节点时，会突出显示依赖于该节点的所有节点以及该节点依赖的所有节点，并且还会显示它们的名称。

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>依赖关系图中的高亮路径不构成选择。

右键单击某节点，可以看到有关图中显示的每个组件的标识信息，并可以选择可用来查看该组件更多详细信息或编辑该组件的菜单选项。此外，您还可以执行文本搜索和显示有关转换和扩展维度的性能信息。

有关依赖关系图的这些功能的信息，请参阅《Data Workbench 用户指南》**&#x200B;的“管理界面”一章。
