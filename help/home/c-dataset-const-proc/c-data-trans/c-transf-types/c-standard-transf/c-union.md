---
description: Union 转换获取一组输入，并创建字符串矢量作为输出。
solution: Analytics
title: Union
topic: Data workbench
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Union{#union}

Union 转换获取一组输入，并创建字符串矢量作为输出。

如果某个输入本身就是一个矢量，则该输入矢量中的每个元素将与输出矢量中的一个元素关联（也就是说，该转换不会创建矢量的矢量）。

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Default（默认值） | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Inputs（输入） | 一个或多个输入值。 |  |
| Output（输出） | 输出字段的名称。 |  |

此示例使用来自网站流量的数据字段创建与网站访客关联的邮政编码列表（即在每个日志条目中）。数据提供此信息的两个可能来源：一个在 cs-uri-query 中，另一个在 Cookie 的 [!DNL zipcode] 字段中。如果这些字段中都不包含邮政编码，则使用默认值 00000。

![](assets/cfg_TransformationType_Union.png)

尽管这两个值都可以在单个日志条目中使用，但在基于转换的输出创建维度时仍可以选择使用哪个值。在典型的使用案例中，您将创建一个简单的维度，以获取遇到的第一个或最后一个值。有关创建简单维度的信息，请参阅 [Extended Dimensions（扩展维度）](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
