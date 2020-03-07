---
description: 可以通过将显示的元素指定为根或向可视化中添加新元素来更改路径浏览器的根。
solution: Analytics
title: 更改路径浏览器的根
topic: Data workbench
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 更改路径浏览器的根{#change-the-path-browser-s-root}

可以通过将显示的元素指定为根或向可视化中添加新元素来更改路径浏览器的根。

>[!NOTE]
>
>不能将开始或结束节点设置为路径浏览器的根。

**设置路径浏览器的根**

* 右键单击所需的元素，然后单击 **[!UICONTROL Set as root]**。

**向路径浏览器中添加新元素**

1. 打开一个图表或表格，该图表或表格显示要在路径浏览器上显示其元素的维度。

   例如，如果您使用网站数据，请打开一个页面图表或表格并标识您要设置为根的页面。

1. 按 Ctrl+Alt 并将所需的元素拖动到路径浏览器上的根位置。

   >[!NOTE]
   >
   >通过将所需维度的元素拖动到路径浏览器，可以更改与路径浏览器关联的基本维度。 此元素便成为该路径浏览器的新根，并且该路径浏览器左上角的标签会发生更改，以反映此元素的维度。

   例如，假设您创建一个显示“每个会话的页面顺序”的页面路径浏览器。如果您将“搜索词”维度的元素拖动到该路径浏览器，则搜索词元素就会成为新的根，并且标签现在将显示“每个会话的搜索词顺序”。

   >[!NOTE]
   >
   >将元素拖动到路径浏览器可能会更改与路径浏览器关联的基本维，但不会更改级别维、组维或度量。 因此，必须格外小心地选择与路径浏览器的级别维度、组维度和量度一起使用时有意义的基本维度。To change the level dimension, group dimension, or metric, you must edit the path browser’s [!DNL *.vw] file in a text editor such as Notepad. See [Configuring Path Browsers](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

