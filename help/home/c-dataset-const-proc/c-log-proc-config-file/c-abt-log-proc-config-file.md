---
description: Log Processing.cfg 文件控制数据集构建的日志处理阶段，在该阶段中，系统将从数据源（也称为日志源）中读取无序数据，并且会对数据应用过滤器和转换。
title: 关于日志处理配置文件
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 69%

---

# 关于日志处理配置文件{#about-the-log-processing-configuration-file}

Log Processing.cfg 文件控制数据集构建的日志处理阶段，在该阶段中，系统将从数据源（也称为日志源）中读取无序数据，并且会对数据应用过滤器和转换。

您必须编辑 [!DNL Log Processing.cfg] 文件才能执行下列任意数据集配置任务：

* 指定日志源。 请参阅[日志源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md)。
* 确定哪些日志条目在日志处理期间输入数据集。 请参阅[数据过滤器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)和[日志条目条件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)。

* 启用具有大量事件数据的跟踪ID的拆分。 请参阅[键拆分](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)。
* 配置 Data Workbench Server，使其作为文件服务器单元运行。请参阅 [配置 Insight Server 文件服务器单元](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* 配置 Data Workbench Server，使其作为集中标准化服务器运行。请参阅 [配置 Insight Server 文件服务器单元](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] 文件可以包含数据集构建的日志处理阶段的其他说明。这些文件存在于任何继承配置文件的 Dataset\Log Processing 目录之内。它们通常定义特定于应用程序的参数（例如，Site 应用程序中特定于 Web 的配置参数）。有关[!DNL Log Processing Dataset Include]文件的信息，请参阅[数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。 有关Site特定于Web的配置参数的信息，请参阅[Web数据的配置设置](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)。
