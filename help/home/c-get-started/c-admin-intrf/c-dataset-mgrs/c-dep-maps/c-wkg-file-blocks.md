---
description: 在依赖关系图中显示数据集组件时，您可以选择启用“包含文件块”显示选项。
solution: Analytics
title: 文件块
topic: Data workbench
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 文件块{#file-blocks}

在依赖关系图中显示数据集组件时，您可以选择启用“包含文件块”显示选项。

启用该选项之后，图中会显示一个蓝色节点（表示一个数据集配置文件中定义的所有转换）和一个绿色节点（表示一个数据集配置文件中定义的所有扩展维度）。For example, if a [!DNL log processing dataset include] file includes the definitions of three transformations, the map displays one blue node representing the three transformations. Similarly, if a [!DNL transformation dataset include] file includes the definitions of two extended dimensions, the map displays one green node representing the two extended dimensions.

## Transformation blocks {#section-c442730394264a0b850792a32eaaa2da}

每个蓝色节点都是一个转换块，并具有以下选项：

* To view the input fields of the transformation block, right-click the node for the block and click **[!UICONTROL Inputs]**.
* To view the output fields of the transformation block, right-click the node for the block and click **[!UICONTROL Outputs]**.
* To edit any of the transformations in the block, right-click the node for the block and click **[!UICONTROL Edit Configuration]**. 显示的标注包含在其中定义所有转换的整个配置文件。随后您可以根据需要编辑这些参数。有关这些参数的详细信息，请参阅《数据集配置指南》**。

* To see all of the transformations in the block, right-click the node for the transformation block and click **[!UICONTROL Show Details]**. 显示的标注包含另一个显示块中所有转换节点的依赖关系图。

## Dimension blocks {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

每个绿色节点都是一个维度块，并具有以下选项：

* To view the input fields or the parent dimension of the dimension block, right-click the node for the block and click **[!UICONTROL Inputs]**.
* To view the output dimensions of the dimension block, right-click the node for the block and click **[!UICONTROL Outputs]**.

