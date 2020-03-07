---
description: Transformation.cfg 文件控制数据集构建的转换阶段，在该阶段中，系统会对已在日志处理过程中处理的数据应用额外的数据转换，以创建要在分析中使用的扩展维度。
solution: Analytics
title: 关于转换配置文件
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 关于转换配置文件{#about-the-transformation-configuration-file}

Transformation.cfg 文件控制数据集构建的转换阶段，在该阶段中，系统会对已在日志处理过程中处理的数据应用额外的数据转换，以创建要在分析中使用的扩展维度。

您必须编辑 [!DNL Transformation.cfg] 文件才能执行下列任意数据集配置任务：

* Filtering data from log processing by defining the [!DNL log entry condition] for transformation.
* 设置用于创建时间维度和进行时间转换的时区。 请参 [阅时区](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956)。

>[!NOTE]
>
>[!DNL Transformation Dataset Include] 文件可以包含有关数据集构建的转换阶段的其他说明。 这些文件位于任何继承配置文件的 Dataset\Transformation 目录内，并且通常定义特定于应用程序的参数（例如[!DNL Site] 应用程序的特定于 Web 的配置参数）。有关文件的 [!DNL Transformation Dataset Include] 信息，请参阅 [数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。 有关站点的Web特定配置参数的信息，请参阅Web [数据的配置设置](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

