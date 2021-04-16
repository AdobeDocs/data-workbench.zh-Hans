---
description: 您可以自定义菜单外观，包括工作区窗口菜单（右键单击任意工作区即可访问）和列出量度、维度和映射图层的菜单。
title: 自定义菜单
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 71%

---

# 自定义菜单{#customize-a-menu}

您可以自定义菜单外观，包括工作区窗口菜单（右键单击任意工作区即可访问）和列出量度、维度和映射图层的菜单。

任何菜单的层次结构都反映了[!DNL Profile Manager]中其目录的结构。 例如，工作区窗口菜单反映了 Menu 目录结构，量度菜单则反映了 Metrics 目录结构。任何菜单对应的目录都可能包含以下项目：

* **文件：**&#x200B;这些文件表示您可以通过单击相应的菜单项打开的可视化、图例、批注、管理界面、量度、维度或映射图层。
* **[!DNL order.txt] 文件：**&#x200B;此文件指定菜单显示其项目的顺序。
* **子目录：**&#x200B;每个子目录表示一个子菜单。每个子目录可以包含其自身的文件、子目录和 [!DNL order.txt] 文件。

例如，[!DNL Add Legend]菜单按该顺序包含菜单项Metric、Color、Value和Confide。 相比之下，[!DNL Profile Manager]中的Menu\Add Legend目录包含按字母顺序排列的文件[!DNL Color.vw]、[!DNL Confidence.vw]、[!DNL Metric.vw]和[!DNL Value.vw]，以及控制其他文件顺序的[!DNL order.txt]文件。
