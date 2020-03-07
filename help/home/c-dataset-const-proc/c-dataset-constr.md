---
description: Adobe 数据集包含由 Data Workbench Server 加载并处理过的数据。
solution: Analytics
title: 了解数据集构建
topic: Data workbench
uuid: 540d159d-3f72-49dd-9929-107f1fc62b2b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 了解数据集构建{#understanding-dataset-construction}

Adobe 数据集包含由 Data Workbench Server 加载并处理过的数据。

数据集构建过程包含由 Data Workbench Server (InsightServer64.exe) 加载并处理数据时所涉及的步骤。

>[!NOTE]
>
>处理和服务来自Adobe数据集的数据的Data Workbench Server称为数据处理单元或DPU。 它有时又称为处理服务器或查询服务器。Data workbench and [!DNL Report] clients interact with DPUs directly.

在数据集构建过程中，Data Workbench Server 从日志源读取源数据，对特定的数据字段应用转换，并定义要从转换字段创建的扩展维度。构建过程包括以下两个阶段： 日志 *处理* 和 *转换*。 构建数据集之后，您可以使用数据集的扩展维度来创建派生量度和维度，以便进行具体的分析。

数据集构建就像是一个生产过程。您选择要用于构建数据集的数据（原材料），然后定义用于处理数据中提供信息的数据转换（加工步骤）来创建扩展维度（生产的产品）。

<!--
c_log_proc.xml
-->

系统会过滤日志，并识别要传递到转换阶段的数据字段。在日志处理阶段结束时，数据会按跟踪 ID 进行分组（即所有具有相同跟踪 ID 的日志条目会分成一组），并按时间进行排序。在日志处理阶段，您无法访问已处理的数据以供分析使用。

## 指定日志源 {#section-75279dd6a7304d469735562796741d0f}

日志源是指包含要用于构建数据集的数据的文件。日志源中提供的数据称为事件数据，因为每条数据记录都表示一条交易记录或一个事件的单个实例。此外，每条记录（日志条目）都包含一个称为跟踪 ID 的值。

>[!NOTE]
>
>选择日志源时，请确保每个日志条目都包含实体的跟踪ID，该ID表示要将数据分组到的最高级别。 例如，如果您要处理从网站流量收集的数据，则可能会选择访客作为此实体。每个访客都有一个唯一的跟踪 ID，并且所有关于特定网站访客的数据都可分为一组。要寻求帮助，请联系 Adobe。

A log sources event data is collected in real-time by [!DNL Sensors] or extracted from archived data sources by Insight Server. Event data collected by Sensors from HTTP and application servers is transmitted to Insight Servers, which convert the data into highly compressed log ( [!DNL .vsl]) files. Insight Server 可读取位于无格式文件、XML 文件或 ODBC 数据源中的事件数据，并提供您定义的解码器来从这些不同的格式中提取通用的数据字段集。

## 定义转换 {#section-55a8cdb47379484081e53087f074778d}

转换是一组指令，您可以对其进行定义以提取或处理事件数据中的信息。您定义的每个转换都会应用于每条事件数据记录（日志条目），以更新现有日志字段或生成新字段。转换结果会与日志条目条件一起使用，用来评估将在日志处理过程中从数据集过滤出的日志条目。

并非所有类型的转换都可以在数据集构建过程的日志处理阶段使用。

## 过滤日志 {#section-6172ca0fb0eb4177925151bb49fdbc02}

数据集包含几个参数，用于过滤从转换流出的数据。过滤用来指定要在后续处理步骤中使用的日志条目。例如，可以按时间范围、服务器响应的状态或 IP 地址和用户代理信息定义过滤器。这是一 [!DNL Log Entry Condition] 个可自定义的过滤测试。 该测试会在每个日志条目的字段中查找特定的条件来确定该条目是否应在数据集构建过程中得到进一步处理。如果某个日志条目不符合条件，则会从构建过程中删除该条目。

## 识别转换字段 {#section-eef98ca723e54547b887aefdf0514c47}

如果某个数据字段要从日志处理阶段传递到转换阶段以便进一步处理，您必须在日志处理过程中识别该字段。无论字段是从日志源获取的还是在日志处理过程中从应用于数据的数据转换创建的，此要求都适用。

<!--
c_transformation.xml
-->

在数据集构建的转换阶段，需要对从日志处理过程中输出的已分组和已排序数据进行处理。此时会执行额外的数据转换，并且会创建扩展数据维度以供您在分析中使用。在转换阶段，您可以访问数据的统计样本，在转换阶段接近完成时该数据会变得更大。

## 定义转换 {#section-001b3fd4c1dd4dd38a5536872bc9de68}

您可以将转换定义为在数据集构建过程的转换阶段使用，以便创建扩展维度。每个转换都会应用于每条从日志处理过程传递的事件数据记录（日志条目）。

## 过滤日志 {#section-3fed0a00ca344a719b5e8db363f64f06}

The [!DNL Log Entry Condition] can be applied during transformation to look for specific conditions in the fields of each log entry coming from log processing. 如果某个日志条目不符合条件，则会从构建过程中删除该条目。

## 定义扩展维度 {#section-25efafd0bfc84c86b9717d453a88c91b}

扩展维度是数据集构建过程的最终产物，它们表示数据中日志字段之间的关系。您可以使用它们创建可视化、构建扩展量度或执行分析，以了解特定于您的业务的操作和问题。
