---
description: 以Excel文件形式生成报表的信息。
title: 将报表生成为 Microsoft Excel 文件
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 20%

---

# 将报表生成为 Microsoft Excel 文件{#generating-reports-as-microsoft-excel-files}

{{eol}}

以Excel文件形式生成报表的信息。

必须满足以下要求：

* [!DNL Report Server] 所在的计算机上必须同时安装了 Microsoft Excel。
* 运行 [!DNL Report Server] 进程的用户帐户必须拥有 Microsoft Excel 的访问权限。

   >[!NOTE]
   >
   >
   >
   >
   >    * 将报表生成为Excel文件时，将打开一个Excel的新实例。 有关此过程的更多信息，请参阅 [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * 尽管Data Workbench支持超过256列和65,536行数据，但Microsoft Excel不支持。


如果满足这些要求， [!DNL Report Server] 自动启动Microsoft Excel并将某些可视化、维度和值图例以及文本批注中的数据输出到新的Excel工作簿中，每个工作表具有一个可视化。

>[!NOTE]
>
>不会导出图表、路径浏览器、流程图、散点图和地球中的数据。

除非您指定了 [!DNL Custom Title] 对于可视化，窗口类型（例如，“影片表”）将用作工作表名称。

有关指定 [!DNL Custom Titles] 对于可视化，请参阅 [Data Workbench客户端指南](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=zh-Hans).

## 使用模板文件 {#section-40ab11916f464b1a88214ab969da6751}

您还可以使用模板Excel( [!DNL .xls] 或 [!DNL .xlsx])文件。 使用模板文件可减少每次生成报表时为数据设置格式所花费的时间。

此模板文件必须是 [!DNL .xls] 或 [!DNL .xlsx] 文件，而不是 [!DNL .xlt] 文件。

您可以选择为每个报表定义模板，为所有报表定义通用模板，或同时定义两者的组合。 这两个项目不是互斥的，因此您可以定义通用模板，然后定义特定模板。

要使用用于所有报表的通用模板生成报表，必须在的“默认Excel模板”参数中指定该Excel文件的名称(位于 [!DNL Report.cfg] 对于该报表集文件，将模板文件放在与 [!DNL Report.cfg] (*data workbench安装目录*\*ProfileName*\Reports\*ReportSetName*)。 有关此参数的信息，请参阅 [Report.cfg参数](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

要使用特定于报表的模板生成报表，必须将Excel文件命名为与报表工作区相同的名称( [!DNL .vw])文件，然后将模板文件放置在与报表工作区相同的文件夹中( [!DNL .vw])文件。

生成报表时，模板中的现有选项卡式工作表（每个表示一个可视化）将重新填充报表中的最新数据，而模板中不存在的任何作为选项卡式工作表的新窗口将被忽略。 模板文件中的任何其他选项卡式工作表都保持不变。

此外，如果您在模板 Excel 文件中定义了要在生成报表时自动运行的宏，则将该宏命名为“VSExport”。
