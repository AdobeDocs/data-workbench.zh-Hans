---
description: 可以将工作区导出为 .png 图像文件，或将某些窗口的数据导出到 Excel（.xls 或 .xlsx）文件。
solution: Analytics
title: 导出工作区
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 导出工作区{#export-a-workspace}

可以将工作区导出为 .png 图像文件，或将某些窗口的数据导出到 Excel（.xls 或 .xlsx）文件。

## 将工作区导出为PNG文件 {#section-f9fbe0f0a1c341e2b063cce106cac35e}

You can save a snapshot of a workspace in Portable Network Graphic format (`.png` files). The following color options are available when saving workspaces as `.png` files:

* **黑色背景**&#x200B;复制显示的工作区。
* **白色背景**&#x200B;用彩色复制工作区的元素并将其显示在白色背景上。
* **白色背景 (B&amp;W)** 用灰度复制工作区的元素并将其显示在白色背景上。

**将工作区导出为 .png 文件**

在工作区的标题栏菜单中，单击 **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*。

将出 [!UICONTROL Save Image As] 现对话框。

Navigate to the directory in which you want to save the file, change the name of the file if necessary, and click **[!UICONTROL Save]**.

## Export workspace data to Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

将工作区导出到 Excel 时，Data Workbench 会将某些可视化、维度和值图例以及文本批注中的数据导出到新的 Excel 工作簿，并且每个工作表对应一个可视化。

若要将工作区和单个窗口导出到 Microsoft Excel，必须满足以下要求：

* Microsoft Excel必须与Data Workbench安装在同一台计算机上。
* 运行数据工作台进程的用户帐户必须具有访问Microsoft Excel的权限。

>[!NOTE]
>
>* 在将数据导出为 Excel 文件时，将打开 Excel 的新实例。有关此过程的详细信息，请参阅 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。
>* 尽管Data Workbench支持超过256列和65,536行数据，但8.0之前的Microsoft Excel版本不支持。
>



如果满足这些要求，Data Workbench将自动启动Microsoft Excel并将数据导出到新的Excel工作簿。 不会导出以下可视化中的数据：图表、路径浏览器、流程图、散点图和地球。

## 应用自定义标题 {#section-a332e157554546cb8e88922a8d7a4fa2}

Unless you have specified a Custom title for the window on the [!UICONTROL Export] menu, the [!UICONTROL Export title] listed (for example, City Table) is used as the worksheet name.

1. Right-click the top border of the window and click in the **[!UICONTROL Custom title]** field.
1. 键入您要应用于窗口的标题。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>If you enter a hyphen (-) in the [!UICONTROL Custom title] field, this visualization is not exported with the workspace.

When you export the workspace to Excel, the worksheet containing the data for this window is named using the title that you specified instead of the title in the [!UICONTROL Export title] field.

## Export a workspace or sidebar to Excel {#section-360438b66d5f4734826ab463b4a01a75}

**将工作区数据导出到新的或文[!DNL .xls]件中[!DNL .xlsx]**

1. In title bar of the workspace, click **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. 指定是导出工作区、侧栏还是两者都导出。

## Export to a template Excel file {#section-814772929ca64cf6b92b89d3fdd02302}

You can export data in your workspace to a template Excel file (`.xls` or `.xlsx`). 使用模板文件可以缩短每次导出工作区时花费在格式化数据上的时间。

>[!NOTE]
>
>This template file must be an `.xls` or `.xlsx` file, not an `.xlt` file.

导出数据时，使用工作区中的最新数据重新填充模板中的现有选项卡式工作表（每个工作表表示一个可视化），但将忽略模板中未以选项卡式表存在的任何新窗口。模板文件中的任何其他选项卡式工作表都保持不变。

此外，如果您在模板 Excel 文件中定义了要在生成报表时自动运行的宏，则将该宏命名为“VSExport”。

例如，您想在 Excel 文件其他选项卡式工作表的饼图中使用从表格可视化导出的营销活动数据，并且想每周更新此信息。那么您可以使用一个模板，从而不必在每次想更新数据时都重新创建从表格的选项卡式工作表到饼图选项卡式工作表的引用。表格数据将在导出时进行更新，这会自动更新饼图。

**将工作区数据导出到模板或[!DNL .xls]文件[!DNL .xlsx]中**

1. 右键单击工作区的标题栏，然后单击 **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**。
1. 指定是导出工作区、侧栏还是两者都导出。

   将打 [!UICONTROL Select a template worksheet] 开对话框。

1. 根据需要完成以下步骤之一：

   * If you are using a `.xls` template file:

      1. Browse to and select the template `.xls` file.
      1. 单击 **[!UICONTROL Open]**.
   * If you are using a `.xlsx` template file:

      1. 浏览到模板文件的位置。The `.xlsx` file name is not displayed.
      1. 在字段 [!UICONTROL File name] 中，键入并 `.xlsx` 单击 **[!UICONTROL Open]**。 All `.xlsx` file names display in the file list.

      1. Select the template `.xlsx` file.
      1. 单击 **[!UICONTROL Open]**.


