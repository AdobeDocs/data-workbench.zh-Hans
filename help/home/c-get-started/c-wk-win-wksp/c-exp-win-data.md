---
description: 可以将某些窗口的数据导出到 Excel 文件（.xls 或 .xlsx）或导出到制表符分隔值文件 (.tsv) 中。
title: 导出窗口数据
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 34%

---

# 导出窗口数据{#export-window-data}

可以将某些窗口的数据导出到 Excel 文件（.xls 或 .xlsx）或导出到制表符分隔值文件 (.tsv) 中。

不会导出图表、路径浏览器、流程图、散点图和地球中的数据。

## 将窗口数据导出到Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

若要将单个窗口数据导出到 Microsoft Excel，必须满足以下要求：

* 必须将Microsoft Excel安装在与Data Workbench相同的计算机上。
* 运行Data Workbench进程的用户帐户必须具有访问Microsoft Excel的权限。
* 在将数据导出为 Excel 文件时，将打开 Excel 的新实例。
* 尽管Data Workbench支持超过256列和65,536行数据，但8.0之前的Microsoft Excel版本不支持。

如果满足这些要求，当您选择&#x200B;**[!UICONTROL Export To Excel]**&#x200B;菜单选项时，Data Workbench会自动启动Microsoft Excel并将数据导出到新的Excel工作簿。

**将窗口数据导出到 .xls 或 .xlsx 文件**

右键单击窗口的上边框，然后单击&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**。

![](assets/mnu_window_TitleBar_Export.png)

Excel 将打开一个包含导出数据的新工作簿。除非您提供了自定义标题（如以下部分所述），否则此工作簿的名称为[!DNL Export title]（上面示例中的日表）。

## 应用自定义标题{#section-2a6559df812a470685e43923b7b9024e}

如果为窗口提供自定义标题（使用[!DNL Export]菜单上的[!DNL Custom title]字段），则Data Workbench将数据导出到的工作表将使用此自定义标题命名，而不是使用[!DNL Export title]字段中的标题（上例中的日表）。

**将自定义标题应用于可视化**

1. 右键单击窗口的上边框，然后单击&#x200B;**[!UICONTROL Custom title]**&#x200B;字段中的。
1. you

![](assets/mnu_window_TitleBar_Export.png)

将可视化导出到Excel时，将使用您指定的标题（而不是[!DNL Export title]字段中的标题）命名包含此窗口数据的工作表。

## 将窗口数据导出到TSV文件{#section-93c6b24f7338430aaf5a63b99b9489e8}

**将窗口导出到 .tsv 文件**

右键单击窗口的上边框，然后单击&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export TSV]**。

1. 出现[!DNL Save Window]对话框。
1. 导航到要保存文件的目录。如有必要，更改文件名，然后单击&#x200B;**[!UICONTROL Save]**。
