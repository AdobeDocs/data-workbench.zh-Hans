---
description: 要导出的任何数据都必须在配置文件中定义为维度。
title: 创建用于区段导出的维度
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 68%

---

# 创建用于区段导出的维度{#create-dimensions-for-use-with-segment-export}

{{eol}}

要导出的任何数据都必须在配置文件中定义为维度。

如果配置文件中尚不存在维度，则必须创建一个。您可以使用以下任一方法创建维度：

* 向 [!DNL Transformation.cfg] 文件。 请参阅 *数据集配置指南*.

* 新建 [!DNL .dim] 文件。 请参阅 [创建和编辑派生Dimension](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* 在可视化中进行选择（如流程图或区段），并将选择保存为维度。 请参阅 [从流程图保存Dimension](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) 和 [创建区段Dimension](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

导出数据字段（例如“跟踪 ID”或“电子邮件地址”（可能有很多元素））需要创建用于存储数据原始字符串的非正规维度。

有关非正规维度的详细信息，请参阅《数据集配置指南》**。
