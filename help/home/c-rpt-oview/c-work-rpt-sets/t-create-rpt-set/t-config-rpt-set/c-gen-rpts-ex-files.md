---
description: 生成Excel文件格式的报表的信息。
solution: Analytics
title: 将报表生成为Microsoft Excel文件
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# 将报表生成为Microsoft Excel文件{#generating-reports-as-microsoft-excel-files}

生成Excel文件格式的报表的信息。

必须满足以下要求：

* [!DNL Report Server] 所在的计算机上必须同时安装了 Microsoft Excel。
* 运行 [!DNL Report Server] 进程的用户帐户必须拥有 Microsoft Excel 的访问权限。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 将报表生成为Excel文件时，您将打开Excel的新实例。 有关此过程的详细信息，请参阅 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。
   >    * 尽管Data Workbench支持超过256列和65,536行数据，但Microsoft Excel不支持。


如果满足这些要求，将自动启动Microsoft Excel，并将某些可视化、维度和值图例以及文本注释的数据输出到新的Excel工作簿，每个工作表有一个可视化。 [!DNL Report Server]

>[!NOTE]
>
>不会导出图表、路径浏览器、流程图、散点图和地球中的数据。

除非您为可视 [!DNL Custom Title] 化指定了窗口类型（例如，“电影表”），否则将用作工作表名称。

有关为可视化指定 [!DNL Custom Titles] 的详细信息，请参 [阅《Data Workbench客户端指南》](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html)。

## 使用模板文件 {#section-40ab11916f464b1a88214ab969da6751}

您还可以使用模板Excel（或）文件将报表生成为Excel [!DNL .xls] 文 [!DNL .xlsx]件。 使用模板文件可以减少每次生成报告时您花费在格式化数据上的时间。

This template file must be an [!DNL .xls] or [!DNL .xlsx] file, not an [!DNL .xlt] file.

您可以选择为每个单独的报表定义一个模板，为所有报表定义一个通用模板，或同时定义两者的组合。 这两个项目不是互斥的，因此您可以定义通用模板，然后也可以定义特定模板。

要使用用于所有报表的通用模板生成报表，必须在报表集文件的“默认Excel模板”参数中指定该Excel文件的名称，然后将模板文件放在该报表集的同一文件夹中( [!DNL Report.cfg] Data Workbench安装目录 [!DNL Report.cfg]**\*ProfileName*\Reports\*ReportSetName*)。 有关此参数的信息，请参 [阅Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

要使用特定于报表的模板生成报表，必须将Excel文件命名为与报表工作区( [!DNL .vw])文件相同的文件，然后将模板文件放在与报表工作区( [!DNL .vw])文件相同的文件夹中。

生成报告后，模板中的现有选项卡式工作表（每个表示一个可视化）将重新填充报告中的最新数据，而模板中不存在作为选项卡式工作表的任何新窗口将被忽略。 模板文件中的任何其他选项卡式工作表都保持不变。

此外，如果您在模板 Excel 文件中定义了要在生成报表时自动运行的宏，则将该宏命名为“VSExport”。
