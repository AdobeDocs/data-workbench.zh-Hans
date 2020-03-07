---
description: Copy 转换仅将输入字段中的值复制到给定的输出字段。如果输入字段可能为字符串矢量，则输出字段必须以“x-”开头。
solution: Analytics
title: Copy
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copy{#copy}

Copy 转换仅将输入字段中的值复制到给定的输出字段。如果输入字段可能为字符串矢量，则输出字段必须以“x-”开头。

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Default（默认值） | 如果条件测试为 true，但输入值在给定日志条目中不可用，则使用此值。 |  |
| Input（输入） | 从中进行复制的字段名称。 |  |
| Output（输出） | 输出字段的名称。 |  |

In this example, which uses fields of data collected from website traffic, the output field, x-purchase-success, is given the literal value of &quot;1&quot; each time cs-uri-stem matches [!DNL /checkout/confirmed.php]. If the [!DNL Condition] is not satisfied (that is, cs-uri-stem does not match [!DNL /checkout/confirmed.php]), x-purchase-success is not changed.

![](assets/cfg_TransformationType_Copy.png)

