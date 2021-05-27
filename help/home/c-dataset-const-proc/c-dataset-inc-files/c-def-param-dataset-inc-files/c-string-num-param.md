---
description: 字符串参数和数值参数分别将字符串和数值作为其各自的值。
title: 字符串参数和数值参数
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
exl-id: 37d004da-cde7-4b67-b0cb-0acbb6d8ad68
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 74%

---

# 字符串参数和数值参数{#string-and-numeric-parameters}

字符串参数和数值参数分别将字符串和数值作为其各自的值。

这两种参数可以换用，但数值参数必须定义为具有数值。您可以在定义转换、条件和扩展维度时引用字符串参数和数值参数，还可以在同一行中引用多个参数。

不能在[!DNL Input]或[!DNL Output]字段中引用字符串参数和数字参数，但可以使用字符串参数定义常量输入字段。 此外，还不能在解码器或解码器组中引用字符串参数和数值参数。

此示例显示一个[!DNL Log Processing Dataset Include]文件，其中定义了字符串参数和数字参数。 请注意，名为“Value Lookups”的字符串参数定义了相对于 Data Workbench Server 安装目录的文件位置 (Lookups\Values)。

![](assets/cfg_Parameters_StringNumeric.png)
