---
description: Flatten 转换获取字符串矢量，并将每个值映射到其自身的字段中。
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 99%

---

# Flatten{#flatten}

Flatten 转换获取字符串矢量，并将每个值映射到其自身的字段中。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 在满足条件但输入值不可用于日志条目时所使用的默认值。 |  |
| Input（输入） | 要映射到输出字段名称的字符串值矢量。 |  |
| Outputs（输出） | 一组输出字段名称。 |  |

[!DNL Flatten]的注意事项

* 如果输入矢量包含的值比定义的输出字段多，则会直接删除额外的输入值。
* 如果输入矢量包含的值比定义的输出字段少，则会为多余的输出字段指定默认值（如果定义），或者如果未定义默认值，则将指定空字符串。

这里的 [!DNL Flatten] 转换用于获取产品 (x-products) 的矢量，并将它们分为四个字段（x-product1、...、x-product4）。

![](assets/cfg_TransformationType_Flatten.png)

如果输入值包含字符串 B57481、C46355 和 Z97123，则输出字段将具有如下所示的值：

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Empty（输入比输出多，且未指定默认值。）
