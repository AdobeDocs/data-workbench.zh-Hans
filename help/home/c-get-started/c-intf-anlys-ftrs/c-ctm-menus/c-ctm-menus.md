---
description: 您可以自定义菜单外观，包括工作区窗口菜单（右键单击任意工作区即可访问）和列出量度、维度和映射图层的菜单。
solution: Analytics
title: 自定义菜单
topic: Data workbench
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 自定义菜单{#customize-a-menu}

您可以自定义菜单外观，包括工作区窗口菜单（右键单击任意工作区即可访问）和列出量度、维度和映射图层的菜单。

The hierarchy of any menu mirrors the structure of its directory in the [!DNL Profile Manager]. 例如，工作区窗口菜单反映了 Menu 目录结构，量度菜单则反映了 Metrics 目录结构。任何菜单对应的目录都可能包含以下项目：

* **文件：**&#x200B;这些文件表示您可以通过单击相应的菜单项打开的可视化、图例、批注、管理界面、量度、维度或映射图层。
* **[!DNL order.txt]文件：**&#x200B;此文件指定菜单显示其项目的顺序。
* **子目录：**&#x200B;每个子目录表示一个子菜单。每个子目录可以包含其自身的文件、子目录和 [!DNL order.txt] 文件。

For example, the [!DNL Add Legend] menu contains the menu items Metric, Color, Value, and Confidence, in that order. In comparison, the Menu\Add Legend directory in the [!DNL Profile Manager] contains the files [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw], and [!DNL Value.vw] files in alphabetical order, as well as an [!DNL order.txt] file to control the order of the other files.
