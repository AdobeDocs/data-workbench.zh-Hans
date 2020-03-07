---
description: 可以从图表、表格或流程图创建路径浏览器。
solution: Analytics
title: 创建路径浏览器
topic: Data workbench
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creating path browsers{#creating-path-browsers}

可以从图表、表格或流程图创建路径浏览器。

**从图表或表格创建路径浏览器**

1. 向工作区中添加路径浏览器。该可视化除了左上角的标签（“序列...”）之外全是空白。
1. 打开一个图表或表格，该图表或表格显示要在路径浏览器上显示其元素的维度。例如，如果您使用网站数据，请打开一个页面图表或表格并标识您要设置为根的页面。
1. 按 Ctrl+Alt 并将所需的元素拖动到路径浏览器。路径浏览器左上角的标签会发生更改，以反映您将其元素拖动到路径浏览器的基本维度。

>[!NOTE]
>
>将元素拖动到路径浏览器可能会更改与路径浏览器关联的基本维，但不会更改级别维、组维或度量。 因此，必须格外小心地选择与路径浏览器的级别维度、组维度和量度一起使用时有意义的基本维度。To change the level dimension, group dimension, or metric, you must edit the path browser’s [!DNL *.vw] file in a text editor such as Notepad. See [Configuring Path Browsers](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**从流程图创建路径浏览器**

>[!NOTE]
>
>从流程图创建的路径浏览器仅显示流程图中显示的元素。 不显示基本维度的其他元素。

1. 创建流程图。 See [Creating Process Maps](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. 将所需的元素从流程图拖动到路径浏览器。该元素就变成了路径浏览器的根。

>[!NOTE]
>
>从流程图创建路径浏览器时，路径浏览器会忽略级别维的元素，而没有关联的基本维元素。 当将一个节点从流程图拖动到路径浏览器上时，路径浏览器的基本维度（名为“网站地图”）由该流程图定义，并且其元素仅限该流程图上的元素。因此，路径浏览器级别维度的某些元素没有关联的基本维度元素并且不在路径浏览器中表示。
