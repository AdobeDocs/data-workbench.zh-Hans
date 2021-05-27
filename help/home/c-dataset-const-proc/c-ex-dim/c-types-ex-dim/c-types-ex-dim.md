---
description: Insight Server 允许您定义要在数据集中包含的可计数、简单、多对多、数值、非正规和时间维度。
title: 扩展维度的类型
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 91%

---

# 扩展维度的类型{#types-of-extended-dimensions}

Insight Server 允许您定义要在数据集中包含的可计数、简单、多对多、数值、非正规和时间维度。

每种维度类型都有一组参数，您可以编辑这些参数的值来提供特定说明，以供 Insight Server 在数据集构建的转换阶段创建维度。

虽然某些参数因维度类型而不尽相同，但所有类型都需要指定父维度（Parent（父项）参数）。父维度确定日志源中的哪些日志条目作为新维度的输入提供。换言之，在应用任何过滤之前，与父维度的元素关联的日志条目也就是将与新维度关联的条目。父维度还确定新维度在数据集层次结构（也称为数据集架构）内的位置。有关显示数据集架构的界面信息，请参阅 [数据集配置工具](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Insight Server 使用父维度确定创建维度时应考虑的日志条目之后，将指定条件（Condition（条件）参数）应用到不满足条件的日志条目。然后，服务器标识每个日志条目的指定输入字段（Input（输入）参数）的值，并应用指定的运算（Operation（运算）参数）（如果适用）。

>[!NOTE]
>
>如果日志条目不满足扩展维度的“条件”，则Insight Server会将空白值替换为日志条目中的所有字段。 实际的日志条目仍然存在，并且指定的 Operation（运算）参数会确定是否将使用 [!DNL Input]（输入）字段的空白值。
