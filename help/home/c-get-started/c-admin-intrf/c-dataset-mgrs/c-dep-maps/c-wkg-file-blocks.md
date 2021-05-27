---
description: 在依赖关系图中显示数据集组件时，您可以选择启用“包含文件块”显示选项。
title: 文件块
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 51%

---

# 文件块{#file-blocks}

在依赖关系图中显示数据集组件时，您可以选择启用“包含文件块”显示选项。

启用该选项之后，图中会显示一个蓝色节点（表示一个数据集配置文件中定义的所有转换）和一个绿色节点（表示一个数据集配置文件中定义的所有扩展维度）。例如，如果[!DNL log processing dataset include]文件包含三个转换的定义，则映射将显示一个表示三个转换的蓝色节点。 同样，如果[!DNL transformation dataset include]文件包含两个扩展维度的定义，则映射将显示一个表示两个扩展维度的绿色节点。

## 转换块{#section-c442730394264a0b850792a32eaaa2da}

每个蓝色节点都是一个转换块，并具有以下选项：

* 要查看转换块的输入字段，请右键单击该块的节点，然后单击&#x200B;**[!UICONTROL Inputs]**。
* 要查看转换块的输出字段，请右键单击该块的节点，然后单击&#x200B;**[!UICONTROL Outputs]**。
* 要编辑块中的任何转换，请右键单击块的节点，然后单击&#x200B;**[!UICONTROL Edit Configuration]**。 显示的标注包含在其中定义所有转换的整个配置文件。随后您可以根据需要编辑这些参数。有关这些参数的详细信息，请参阅《数据集配置指南》**。

* 要查看块中的所有转换，请右键单击转换块的节点，然后单击&#x200B;**[!UICONTROL Show Details]**。 显示的标注包含另一个显示块中所有转换节点的依赖关系图。

## Dimension块{#section-0dd581ac6dfc4153bee5300b3cfae2a0}

每个绿色节点都是一个维度块，并具有以下选项：

* 要查看维度块的输入字段或父维度，请右键单击该块的节点，然后单击&#x200B;**[!UICONTROL Inputs]**。
* 要查看维度块的输出维度，请右键单击该块的节点，然后单击&#x200B;**[!UICONTROL Outputs]**。
