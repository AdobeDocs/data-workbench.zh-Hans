---
description: 可以将工作区导出为 .png 图像文件，或将某些窗口的数据导出到 Excel（.xls 或 .xlsx）文件。
title: 导出工作区
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 53%

---

# 导出工作区{#export-a-workspace}

可以将工作区导出为 .png 图像文件，或将某些窗口的数据导出到 Excel（.xls 或 .xlsx）文件。

## 将工作区导出为PNG文件 {#section-f9fbe0f0a1c341e2b063cce106cac35e}

可以以可移植网络图形格式（`.png`文件）保存工作区的快照。 将工作区另存为`.png`文件时，可以使用以下颜色选项：

* **黑色背景**&#x200B;复制显示的工作区。
* **白色背景**&#x200B;用彩色复制工作区的元素并将其显示在白色背景上。
* **白色背景 (B&amp;W)** 用灰度复制工作区的元素并将其显示在白色背景上。

**将工作区导出为 .png 文件**

在工作区的标题栏菜单中，单击&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > ***[!UICONTROL color option]**>*。

此时会显示 [!UICONTROL Save Image As] 对话框。

导航到要在其中保存文件的目录，根据需要更改文件名，然后单击&#x200B;**[!UICONTROL Save]**。

## 将工作区数据导出到Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

将工作区导出到 Excel 时，Data Workbench 会将某些可视化、维度和值图例以及文本批注中的数据导出到新的 Excel 工作簿，并且每个工作表对应一个可视化。

若要将工作区和单个窗口导出到 Microsoft Excel，必须满足以下要求：

* Microsoft Excel必须与Data Workbench安装在同一台计算机上。
* 运行Data Workbench进程的用户帐户必须具有访问Microsoft Excel的权限。

>[!NOTE]
>
>* 在将数据导出为 Excel 文件时，将打开 Excel 的新实例。有关此过程的更多信息，请参阅[https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757)。
>* 尽管Data Workbench支持超过256列和65,536行数据，但8.0之前的Microsoft Excel版本不支持。
>


如果满足这些要求，Data Workbench会自动启动Microsoft Excel并将数据导出到新的Excel工作簿。 不会导出以下可视化中的数据：图表、路径浏览器、流程图、散点图和地球。

## 应用自定义标题 {#section-a332e157554546cb8e88922a8d7a4fa2}

除非您在[!UICONTROL Export]菜单上为窗口指定了自定义标题，否则将使用列出的[!UICONTROL Export title]（例如，城市表）作为工作表名称。

1. 右键单击窗口的上边框，然后单击&#x200B;**[!UICONTROL Custom title]**&#x200B;字段中的。
1. 键入您要应用于窗口的标题。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>如果在[!UICONTROL Custom title]字段中输入连字符(-)，则此可视化图表不会与工作区一起导出。

将工作区导出到Excel时，将使用您指定的标题（而不是[!UICONTROL Export title]字段中的标题）命名包含此窗口数据的工作表。

## 将工作区或侧栏导出到Excel {#section-360438b66d5f4734826ab463b4a01a75}

**将工作区数据导出到新 [!DNL .xls] 或文 [!DNL .xlsx] 件**

1. 在工作区的标题栏中，单击&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export]**。
1. 指定是导出工作区、侧栏还是两者都导出。

## 导出到模板Excel文件 {#section-814772929ca64cf6b92b89d3fdd02302}

可以将工作区中的数据导出到模板Excel文件（`.xls`或`.xlsx`）。 使用模板文件可以缩短每次导出工作区时花费在格式化数据上的时间。

>[!NOTE]
>
>此模板文件必须是`.xls`或`.xlsx`文件，而不是`.xlt`文件。

导出数据时，使用工作区中的最新数据重新填充模板中的现有选项卡式工作表（每个工作表表示一个可视化），但将忽略模板中未以选项卡式表存在的任何新窗口。模板文件中的任何其他选项卡式工作表都保持不变。

此外，如果您在模板 Excel 文件中定义了要在生成报表时自动运行的宏，则将该宏命名为“VSExport”。

例如，您想在 Excel 文件其他选项卡式工作表的饼图中使用从表格可视化导出的营销活动数据，并且想每周更新此信息。那么您可以使用一个模板，从而不必在每次想更新数据时都重新创建从表格的选项卡式工作表到饼图选项卡式工作表的引用。表格数据将在导出时进行更新，这会自动更新饼图。

**将工作区数据导出到模板或 [!DNL .xls] 文 [!DNL .xlsx] 件**

1. 右键单击工作区的标题栏，然后单击&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**。
1. 指定是导出工作区、侧栏还是两者都导出。

   将打开[!UICONTROL Select a template worksheet]对话框。

1. 根据需要完成以下步骤之一：

   * 如果您使用的是`.xls`模板文件：

      1. 浏览并选择模板`.xls`文件。
      1. 单击 **[!UICONTROL Open]**。
   * 如果您使用的是`.xlsx`模板文件：

      1. 浏览到模板文件的位置。未显示`.xlsx`文件名。
      1. 在[!UICONTROL File name]字段中，键入`.xlsx`并单击&#x200B;**[!UICONTROL Open]**。 所有`.xlsx`文件名都显示在文件列表中。

      1. 选择模板`.xlsx`文件。
      1. 单击 **[!UICONTROL Open]**。
