---
description: 转换功能（转换）在 Data Workbench Server 计算机上运行，用于导出日志源数据以供其他应用程序使用。
solution: Analytics
title: 关于转换功能
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 关于转换功能{#about-transformation-functionality}

转换功能（转换）在 Data Workbench Server 计算机上运行，用于导出日志源数据以供其他应用程序使用。

[!DNL Transform] 可以读 [!DNL .vsl][!DNL .vsl] 取文件、日志文件、XML文件和ODBC数据，并将数据导出为文件、文本文件或分隔文本文件，这些文件可由数据仓库加载例程、审计机构或其他目标使用。 数据提取和转换可以连续执行，也可以按计划执行。

>[!NOTE]
>
>Typically, [!DNL Transform] is configured on a data workbench server FSU. 但是，您的实施可能需要在 Data Workbench Server DPU 上进行配置。有关详细信息，请联系 Adobe。

You can view memory usage information for [!DNL Transform] in the Detailed Status interface. 有关详细信息，请参阅《Data Workbench 用户指南》**&#x200B;的“管理界面”一章。

区段导出功能提供了另外一种从 Adobe 应用程序导出数据的方式。[!DNL Transform] 允许您将未处理的数据导出到外部目标，但区段导出功能允许您从数据集中输出已处理的数据，并要求将导出的数据定义为数据集中的维。 有关区段导出的详细信息，请参阅《Data Workbench 用户指南》**。
