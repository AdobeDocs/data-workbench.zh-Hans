---
description: 矢量参数包含单个变量的多个值。
solution: Analytics
title: 矢量参数
topic: Data workbench
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 矢量参数{#vector-parameters}

矢量参数包含单个变量的多个值。

只能将矢量参数作为某个矢量的唯一项目引用。This example shows a [!DNL Transformation Dataset Include] file that defines a vector parameter. 矢量参数“Internal Domains”（内部域）包含三个值。

![](assets/cfg_WebParameters_InternalDomains.png)

Note that the vector parameter is the only item listed for the [!DNL Matches] vector in the [!DNL String Match] condition.

![](assets/cfg_Parameters_InternalDomains_Ref.png)

有关内部域的详细信息，请参 [阅Web数据的配置设置](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。 有关该条件的 [!DNL String Match] 信息，请参 [阅条件](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。
