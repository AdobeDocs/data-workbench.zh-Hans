---
description: ReplaceURI 转换将内部 URI 维度中的值更改为新值。
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

ReplaceURI 转换将内部 URI 维度中的值更改为新值。

If [!DNL URI Prefix] is specified, the resulting value is simply the URI prefix concatenated with the provided input value.

| 参数 | 描述 | 默认值 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| Comments（备注） | 可选。有关转换的说明。 |  |
| Condition（条件） | 应用此转换的条件。 |  |
| Default（默认值） | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Input（输入） | 用于替换 URI 的值。 |  |
| URI Prefix（URI 前缀） | 在 [!DNL Input]（输入）字段值前面附加的值（字符串）。 |  |

>[!NOTE]
>
>Before applying [!DNL ReplaceURI] transformations, you should create a new simple dimension with a parent of [!DNL Page View]from a copy of cs-uri-stem or cs-uri. 对此如需帮助，请联系 Adobe。

此示例演示了当 [!DNL ReplaceURI]pageid *指示访客查看了网站的主页时，如何使用* 将“page=[!DNL homepage.html]pageid *”查询字符串替换为“*”。最终结果是更易记的 URI 视图。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

对于所示的转换，网页

* [!DNL www.examplesite.com/info.html?page=1550]

将更改为

* [!DNL www.examplesite.com/homepage.html]

