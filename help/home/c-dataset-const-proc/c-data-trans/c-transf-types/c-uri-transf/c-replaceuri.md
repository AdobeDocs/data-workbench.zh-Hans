---
description: ReplaceURI 转换将内部 URI 维度中的值更改为新值。
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 79%

---

# ReplaceURI{#replaceuri}

ReplaceURI 转换将内部 URI 维度中的值更改为新值。

如果指定了[!DNL URI Prefix]，则结果值只是与提供的输入值连接的URI前缀。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 在满足条件但输入值不可用时所使用的默认值。 |  |
| Input（输入） | 用于替换 URI 的值。 |  |
| URI Prefix（URI 前缀） | 在 [!DNL Input]（输入）字段值前面附加的值（字符串）。 |  |

>[!NOTE]
>
>在应用[!DNL ReplaceURI]转换之前，应从cs-uri-stem或cs-uri的副本创建一个父项为[!DNL Page View]的新简单维度。 对此如需帮助，请联系 Adobe。

此示例演示了当 [!DNL ReplaceURI]pageid *指示访客查看了网站的主页时，如何使用* 将“page=[!DNL homepage.html]pageid *”查询字符串替换为“*”。最终结果是更易记的 URI 视图。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

对于所示的转换，网页

* [!DNL www.examplesite.com/info.html?page=1550]

将更改为

* [!DNL www.examplesite.com/homepage.html]
