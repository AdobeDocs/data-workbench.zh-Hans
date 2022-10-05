---
description: Tokenize 转换针对输入字符串以迭代方式应用正则表达式。
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 89%

---

# Tokenize{#tokenize}

{{eol}}

Tokenize 转换针对输入字符串以迭代方式应用正则表达式。

但是，与 [!DNL RETransform], [!DNL Tokenize] 不必匹配整个字符串：用于 [!DNL Tokenize] 转换可以匹配输入的子集。 在找到匹配项之后，[!DNL Tokenize] 会从上个匹配项结束后的字符处开始再次应用正则表达式。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Case Sensitive（区分大小写） | true 或 false。指定匹配是否区分大小写。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 在满足条件但输入值不可用或正则表达式与输入值不匹配时所使用的默认值。 |  |
| 表达式 | 用于匹配的正则表达式。 |  |
| Outputs（输出） | 输出字符串的名称。对于某个给定的输入字符串，可以有多个输出。输出的数量必须与正则表达式中捕获子模式的数量匹配。 |  |

在以下示例中，[!DNL Tokenize] 转换使用正则表达式捕获查询字符串（在 cs-uri-query 中）的名称，并将捕获的子模式（查询名称）输出到 x-pull-query-name。

![](assets/cfg_TransformationType_Tokenize.png)

对于查询字符串“a=b&amp;c=d”，输出将是一个包含“a”和“c”的矢量。

有关正则表达式的信息，请参阅 [正则表达式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
