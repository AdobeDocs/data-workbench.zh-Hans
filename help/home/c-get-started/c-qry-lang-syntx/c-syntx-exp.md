---
description: 公式的语法规则。
title: 任何表达式的语法
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 77%

---

# 任何表达式的语法{#syntax-for-any-expression}

公式的语法规则。

* 在公式中，关键字区分大小写，键入时必须与其所示完全一致。
* 在公式中，包含空格的量度、维度和过滤器名称必须在字词间使用下划线。例如：[!DNL Page_Views]
* 对于表达式中的字符串，您必须转义某些单引号、双引号和反斜杠。例如：

   * [!DNL “can’t”] 是可以接受的，不需要逃出，但是是不 [!DNL ‘can’t’] 可接受的，必须逃出 [!DNL ‘can\’t’]。

   * [!DNL c:\windows] 必须作为转 [!DNL c:\\windows]义。
