---
description: 关于如何根据若干情景在 Transform.cfg 文件中指定参数的信息。
solution: Analytics
title: Data Workbench Transform.cfg 示例文件
topic: Data workbench
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench Transform.cfg 示例文件{#sample-data-workbench-transform-cfg-files}

关于如何根据若干情景在 Transform.cfg 文件中指定参数的信息。

* [简单 Insight Transform.cfg 文件](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [包含逗号分隔值的输出](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [采样的日志文件](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [按网站区域拆分日志文件](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

在每个示例中，文件都显示为 Data Workbench 中的 [!DNL Transform.cfg] 窗口。

## 简单的 Data Workbench Transform.cfg 文件 {#section-b7e83cafa3a947c597bd09d316930190}

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl] files from the [!DNL Logs] directory and export the x-timestring and x-trackingid fields to a text file stored in the Logs\VT directory. Because no file rotation period or output file name format is specified, each file contains data for one calendar day and has a name in the default format [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## 包含逗号分隔值的输出 {#section-03916934ad574efc8695abbae54a1816}

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl] files from the Logs directory and export fields 0 through 13 to a comma-delimited ( [!DNL .csv]) file stored in the Logs\VT\CSV directory. 由于未指定文件旋转周期，因此每个文件都包含一个日历天的数据。The output files are [!DNL .csv] files named in the format [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## 示例日志文件 {#section-113b3b0c0c7547ea9536bb2f465c0875}

您可以配置转换功能，使其创建并维护完整日志文件的最新精简版本。这样做可让您快速测试数据集配置，只花几秒钟或几分钟时间便可完成重新处理，而不必耗用数小时来重新处理整个数据集。下面提供了如何配置转换功能以实现此操作的示例。

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl] files from the Logs directory and export the x-timestring and x-trackingid fields to a text file stored in the Logs\VT directory. 指定的“哈希阈值”会从数据集中过滤特定的跟踪 ID，从而创建以 100 为系数采样的数据集。由于未指定文件旋转周期，因此每个文件都包含一个日历天的数据。The names of the output files are in the default format [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## 按网站区域拆分日志文件 {#section-2cac205cd3934d31abb6c6ed8780196d}

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl]files from the Logs directory and export the x-timestring and x-trackingid fields to a text file stored in the Logs\VT directory. 正则表达式转换 ([!DNL RETransform]) 采用 cs-uri-stem 字段作为其输入，并创建定义网站区域的新字段 (x-site)。x-site 字段包含在输出文本文件的名称中，其中每个文件都包含一个日历天的数据。

![](assets/cfg_VisualTransform_SplittingExample.png)

