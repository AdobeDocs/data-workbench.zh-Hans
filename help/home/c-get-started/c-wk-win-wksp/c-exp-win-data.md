---
description: 可以将某些窗口的数据导出到 Excel 文件（.xls 或 .xlsx）或导出到制表符分隔值文件 (.tsv) 中。
solution: Analytics
title: 导出窗口数据
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 导出窗口数据{#export-window-data}

可以将某些窗口的数据导出到 Excel 文件（.xls 或 .xlsx）或导出到制表符分隔值文件 (.tsv) 中。

不会导出图表、路径浏览器、流程图、散点图和地球中的数据。

## Export window data to Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

若要将单个窗口数据导出到 Microsoft Excel，必须满足以下要求：

* Microsoft Excel必须与Data Workbench安装在同一台计算机上。
* 运行数据工作台进程的用户帐户必须具有访问Microsoft Excel的权限。
* 在将数据导出为 Excel 文件时，将打开 Excel 的新实例。
* 尽管Data Workbench支持超过256列和65,536行数据，但8.0之前的Microsoft Excel版本不支持。

If these requirements are met, Data Workbench automatically starts Microsoft Excel and export the data to a new Excel workbook when you select the **[!UICONTROL Export To Excel]** menu option.

**将窗口数据导出到 .xls 或 .xlsx 文件**

Right-click the top border of the window and click **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel 将打开一个包含导出数据的新工作簿。Unless you have provided a Custom title (as described in the following section), this workbook is named using the [!DNL Export title] (Day Table in the example above).

## 应用自定义标题 {#section-2a6559df812a470685e43923b7b9024e}

If you provide a custom title for a window (using the [!DNL Custom title] field on the [!DNL Export] menu) the worksheet to which Data Workbench exports the data is named using this custom title instead of the title in the [!DNL Export title] field (Day Table in the example above).

**将自定义标题应用于可视化**

1. Right-click the top border of the window and click in the **[!UICONTROL Custom title]** field.
1. you

![](assets/mnu_window_TitleBar_Export.png)

When you export the visualization to Excel, the worksheet containing the data for this window is named using the title that you specified instead of the title in the [!DNL Export title] field.

## Export window data to a TSV file {#section-93c6b24f7338430aaf5a63b99b9489e8}

**将窗口导出到 .tsv 文件**

Right-click the top border of the window and click **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. 将出 [!DNL Save Window] 现对话框。
1. Navigate to the directory in which you want to save the file. Change the name of the file if necessary, and click **[!UICONTROL Save]**.

