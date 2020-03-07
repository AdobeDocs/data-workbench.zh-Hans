---
description: Unescape URI 转换取消转义字符串中任何已转义的字符。
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# UnescapeURI{#unescapeuri}

Unescape URI 转换取消转义字符串中任何已转义的字符。

>[!NOTE]
>
>转义字符将替换URI字符串中的不安全字符。 它们由三个字符表示，即一个百分号后跟两个十六进制数字（例如 %20）。

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Default（默认值） | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Input（输入） | 要取消转义的 URI 字符串。 |  |
| Output（输出） | 存储取消转义字符串的字段名称。 |  |

以下转换取消转义 HTTP 标头字段中的 docname 值，并将输出存储到字段 x-docname-unescaped 中：

![](assets/cfg_TransformationType_UnescapeURI.png)

如果 docname 值是

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

则 x-docname-unescape 的值将是

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

