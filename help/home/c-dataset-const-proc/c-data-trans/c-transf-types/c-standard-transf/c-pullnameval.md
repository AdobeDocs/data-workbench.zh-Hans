---
description: PullNameValues 转换是一项特殊运算，该运算获取 cs-uri-query 字段中的值，并将每个名称-值对分隔为单独的字符串。
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 84%

---

# PullNameValues{#pullnamevalues}

PullNameValues 转换是一项特殊运算，该运算获取 cs-uri-query 字段中的值，并将每个名称-值对分隔为单独的字符串。

整个名称-值对字符串集作为字符串矢量输出到指定的输出字段中。

| 参数 | 描述 | 默认 |
|---|---|---|
| 名称 | 转换的描述性名称。可以在此处输入任何名称。 |  |
| 评论 | 可选。有关转换的说明。 |  |
| 条件 | 应用此转换的条件。 |  |
| 默认 | 在满足条件但输入值在给定日志条目中不可用时所使用的默认值。 |  |
| Output（输出） | 输出字符串的名称。 |  |

在本示例中，[!DNL PullNameValues] 转换用于捕获访客使用的搜索表单，例如选择了哪些按钮，在表单中键入了什么值，等等。该示例使用[!DNL String Match]条件（请参阅[Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)）将此转换的使用仅隔离到页面[!DNL /search.php]。 名称-值对的矢量是到字段 x-search-namevalues 中的输出。

![](assets/cfg_TransformationType_PullNameValues.png)

如果cs-uri-stem字段与页面[!DNL /search.php]匹配，且cs-uri-query包含以下内容，则使用上面定义的转换：

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

则 x-search-namevalues 将包含一个含有以下三个字符串的矢量：

* Searchfor=Bob
* State=Virginia
* isMale=true
