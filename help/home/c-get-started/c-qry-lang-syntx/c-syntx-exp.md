---
description: 公式的语法规则。
title: 任何表达式的语法
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 77%

---

# 任何表达式的语法{#syntax-for-any-expression}

{{eol}}

公式的语法规则。

* 在公式中，关键字区分大小写，键入时必须与其所示完全一致。
* 在公式中，包含空格的量度、维度和过滤器名称必须在字词间使用下划线。例如：[!DNL Page_Views]
* 对于表达式中的字符串，您必须转义某些单引号、双引号和反斜杠。例如：

   * [!DNL “can’t”] 可接受，且不需要转义，但 [!DNL ‘can’t’] 不可接受，必须转义为 [!DNL ‘can\’t’].

   * [!DNL c:\windows] 必须转义为 [!DNL c:\\windows].
