---
description: 公式的语法规则。
solution: Analytics
title: 任何表达式的语法
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax for any expression{#syntax-for-any-expression}

公式的语法规则。

* 在公式中，关键字区分大小写，键入时必须与其所示完全一致。
* 在公式中，包含空格的量度、维度和过滤器名称必须在字词间使用下划线。例如：[!DNL Page_Views]
* 对于表达式中的字符串，您必须转义某些单引号、双引号和反斜杠。例如：

   * [!DNL “can’t”] 是可接受的，无需转义，但是是不可接 [!DNL ‘can’t’] 受，必须转义为 [!DNL ‘can\’t’]。

   * [!DNL c:\windows] 必须转义为 [!DNL c:\\windows]。

