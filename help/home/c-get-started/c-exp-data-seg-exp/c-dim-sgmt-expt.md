---
description: 要导出的任何数据都必须在配置文件中定义为维度。
solution: Analytics
title: 创建维以便与段导出一起使用
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Create dimensions for use with segment export{#create-dimensions-for-use-with-segment-export}

要导出的任何数据都必须在配置文件中定义为维度。

如果配置文件中尚不存在维度，则必须创建一个。您可以使用以下任一方法创建维度：

* 向文件添加维 [!DNL Transformation.cfg] 度。 请参阅数 *据集配置指南*。

* Create a new [!DNL .dim] file. See [Creating and Editing Derived Dimensions](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* 在流程图或区段等可视化中进行选择，并将选择另存为维。 请参 [阅从流程图保存维](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) 和 [创建区段维](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)。

导出数据字段（例如“跟踪 ID”或“电子邮件地址”（可能有很多元素））需要创建用于存储数据原始字符串的非正规维度。

有关非正规维度的详细信息，请参阅《数据集配置指南》**。
