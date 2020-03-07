---
description: 字符串参数和数值参数分别将字符串和数值作为其各自的值。
solution: Analytics
title: 字符串参数和数值参数
topic: Data workbench
uuid: 2840967e-dd9e-40b2-91e4-3fdfa38f88e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 字符串参数和数值参数{#string-and-numeric-parameters}

字符串参数和数值参数分别将字符串和数值作为其各自的值。

这两种参数可以换用，但数值参数必须定义为具有数值。您可以在定义转换、条件和扩展维度时引用字符串参数和数值参数，还可以在同一行中引用多个参数。

You cannot reference string and numeric parameters in [!DNL Input] or [!DNL Output] fields, but you can use a string parameter to define a constant input field. 此外，还不能在解码器或解码器组中引用字符串参数和数值参数。

This example shows a [!DNL Log Processing Dataset Include] file that defines a string parameter and a numeric parameter. 请注意，名为“Value Lookups”的字符串参数定义了相对于 Data Workbench Server 安装目录的文件位置 (Lookups\Values)。

![](assets/cfg_Parameters_StringNumeric.png)

