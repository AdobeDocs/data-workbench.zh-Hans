---
description: 量度、维度和过滤器表达式可以使用标识符引用命名的量度、维度和过滤器。
title: 标识符的语法
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 100%

---

# 标识符的语法{#syntax-for-identifiers}

{{eol}}

量度、维度和过滤器表达式可以使用标识符引用命名的量度、维度和过滤器。

这些标识符区分大小写，键入时必须与定义的内容完全一致。

有效的标识符可以包含以下一个或多个字符：

* 下划线 (_)。标识符中的下划线表示量度、维度或过滤器名称中的空格。例如， 维度在表达式中表示为 [!DNL Session_Referrer]Session_Referrer。
* 百分号 (%)
* 大写字母 (A-Z)
* 小写字母 (a-z)
* 美元符号 ($)
* 数字 (0-9)，作为标识符中首个字符的情况除外。
* 非 ASCII 字符

所有其他字符在标识符中都为非法字符。

当在表达式之外使用量度、维度或过滤器的名称时，这些规则同样适用于这些名称，只是名称中可以包含空格，但不能包含下划线。例如，您可以在 [!DNL Transformation.cfg] 文件中将 维度定义为 Session Referrer，而不能定义为 [!DNL Session_Referrer]Session_Referrer。
