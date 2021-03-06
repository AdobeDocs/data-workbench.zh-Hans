---
description: 使用转换可提取数据文件中包含的信息并将其处理成更有用的表单格式。
title: 关于转换
uuid: 9366f607-741d-4512-9e1b-4165f4291246
exl-id: 9bd533ef-a87e-400a-9bb0-5af1851cca0a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 91%

---

# 关于转换{#about-transformations}

使用转换可提取数据文件中包含的信息并将其处理成更有用的表单格式。

转换是对日志源中的日志条目（可以将日志条目视为数据行）进行操作。对于每行数据，转换将获取指定输入字段的值，执行一组处理步骤，并将结果记录到指定的输出字段。可以将转换定义为在数据集构建过程的日志处理阶段或转换阶段执行：

* **日志处理期间：**&#x200B;在数据集构建的日志处理阶段执行的转换会应用于每条事件数据记录（日志条目），以更新现有日志字段或生成新字段。转换结果会与日志条目条件一起使用，用来评估将在日志处理过程中从数据集过滤出的日志条目。
* **转换期间：**&#x200B;在数据集构建的转换阶段执行的转换会对从日志处理过程传递的数据字段进行操作，以创建可在分析中使用的扩展维度。请参阅[扩展Dimension](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

>[!NOTE]
>
>从日志处理输入到转换的数据按时间排序，并按源数据中的跟踪ID分组。 某些转换要求数据采用这种形式，并且仅当在转换过程中进行了定义时才可正常使用。

更改转换时务必要小心。转换不影响流入数据集构建过程的日志条目，但它们却会影响显示的结果。这样便允许对分析内容进行更改，而不更改分析所基于的数据。但是，转换中的更改会从根本上改变分析中所生成的值。
