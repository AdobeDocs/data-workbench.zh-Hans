---
description: Transformation.cfg 文件控制数据集构建的转换阶段，在该阶段中，系统会对已在日志处理过程中处理的数据应用额外的数据转换，以创建要在分析中使用的扩展维度。
title: 关于转换配置文件
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 64%

---

# 关于转换配置文件{#about-the-transformation-configuration-file}

{{eol}}

Transformation.cfg 文件控制数据集构建的转换阶段，在该阶段中，系统会对已在日志处理过程中处理的数据应用额外的数据转换，以创建要在分析中使用的扩展维度。

您必须编辑 [!DNL Transformation.cfg] 文件才能执行下列任意数据集配置任务：

* 通过定义 [!DNL log entry condition] 转换。
* 设置用于创建时间维度和进行时间转换的时区。 请参阅 [时区](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] 文件可以包含有关数据集构建转换阶段的其他说明。 这些文件位于任何继承配置文件的 Dataset\Transformation 目录内，并且通常定义特定于应用程序的参数（例如[!DNL Site] 应用程序的特定于 Web 的配置参数）。有关 [!DNL Transformation Dataset Include] 文件，请参阅 [数据集包含文件](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). 有关Site特定于Web的配置参数的信息，请参阅 [Web数据的配置设置](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
