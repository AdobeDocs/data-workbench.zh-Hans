---
description: Copy 转换仅将输入字段中的值复制到给定的输出字段。如果输入字段可能为字符串矢量，则输出字段必须以“x-”开头。
title: 复制
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 76%

---

# 复制{#copy}

{{eol}}

Copy 转换仅将输入字段中的值复制到给定的输出字段。如果输入字段可能为字符串矢量，则输出字段必须以“x-”开头。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 如果条件测试为 true，但输入值在给定日志条目中不可用，则使用此值。 |  |
| Input（输入） | 从中进行复制的字段名称。 |  |
| 输出 | 输出字段的名称。 |  |

在此示例中，使用从网站流量收集的数据字段，每次cs-uri-stem匹配时，输出字段x-purchase-success的文字值为“1” [!DNL /checkout/confirmed.php]. 如果 [!DNL Condition] 不满意(即cs-uri-stem不匹配 [!DNL /checkout/confirmed.php])，则x-purchase-success不会发生更改。

![](assets/cfg_TransformationType_Copy.png)
