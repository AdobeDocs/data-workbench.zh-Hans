---
description: 您可以使用 Hidden（隐藏）参数或 Show（显示）参数来隐藏扩展维度，使其不会显示在 Data Workbench 的维度菜单中。
solution: Analytics
title: 隐藏扩展维度
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 隐藏扩展维度{#hiding-extended-dimensions}

您可以使用 Hidden（隐藏）参数或 Show（显示）参数来隐藏扩展维度，使其不会显示在 Data Workbench 的维度菜单中。

当您输入任一参数的相应设置时，维度名称便不会列在 Data Workbench 的菜单中，但该名称仍位于配置文件中并且可供使用。任何 Data Workbench 用户都可以暂时将隐藏的维度取消隐藏，方法是将 [!DNL Insight.cfg] 文件中的 Unhide All（全部取消隐藏）参数设为 true。

有关 Unhide All（全部取消隐藏）参数的详细信息，请参阅《Data Workbench 用户指南》**&#x200B;中关于 Data Workbench 配置参数的附录。

以下各节描述了如何使用 Hidden（隐藏）和 Show（显示）参数来隐藏扩展维度。

* [使用 Hidden（隐藏）参数隐藏扩展维度](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [使用 Show（显示）参数隐藏扩展维度](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## 使用 Hidden（隐藏）参数隐藏扩展维度 {#section-7167a6f6241a4bc78f2f322e048d65cf}

The Hidden parameter is an optional parameter that you can use when defining extended dimensions in [!DNL Transformation Dataset Configuration] files.

1. Open [!DNL Transformation Dataset Configuration] files in which the extended dimension that you want to hide is defined. See [Editing Existing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. 在配置窗口中找到所需维度对应的 Hidden（隐藏）参数，然后键入 *true*。
1. 将该文件保存在本地，然后将其保存到服务器上的相应配置文件中。请参阅 [编辑现有数据集包含文件](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

数据集将重新转换，然后该扩展维度便不会显示在 Data Workbench 的维度菜单中。有关 Hidden（隐藏）参数的详细信息，请参阅 [Extended Dimensions（扩展维度）](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

如果您更改了 Hidden（隐藏）参数的设置，则必须重新转换数据集才能使更改生效。

## 使用 Show（显示）参数隐藏扩展维度 {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

The Show parameter is not one of the parameters available for defining extended dimensions in [!DNL Transformation Dataset Configuration] files. Instead, the parameter is defined in the [!DNL .dim] files for any derived dimensions that you create. 因此，若要使用 Show（显示）参数来隐藏扩展维度，必须首先按照以下过程所述，创建基于扩展维度的派生维度：

1. 使用文本编辑器（例如记事本）创建一个名为&lt;*维度名称*>.dim 的空文件。该文件名应该与您要隐藏的维度名称匹配。例如，若要隐藏“下一页”维度，您将创建 [!DNL Next Page.dim] 文件。

1. 将以下文本添加到该文件中：

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. 将该文件保存到配置文件的 Dimensions 目录中。如果需要，可以将该文件保存到某个子目录中。

当您使用 Show（显示）参数隐藏扩展维度时，不必重新转换数据集即可使更改生效。You can choose to hide or show the dimension in your local version of the profile (that is, you can save the [!DNL .dim] file to your User folder), or you can save the [!DNL .dim] file to the server for use by other users of the profile.

您也可以使用 Show（显示）参数来隐藏量度和过滤器。有关信息，请参阅《Data Workbench 用户指南》**&#x200B;中的“配置界面和分析功能”一章。
