---
description: 量度、维度和过滤器表达式可以使用标识符引用命名的量度、维度和过滤器。
solution: Analytics
title: 标识符的语法
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax for identifiers{#syntax-for-identifiers}

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
