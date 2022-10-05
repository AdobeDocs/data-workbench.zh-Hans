---
description: 通过关联矩阵中的二进制过滤器，您可以限制其中一个或两个关联量度的值以更好地进行比较。
title: 关联矩阵中的二进制过滤器
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 55%

---

# 关联矩阵中的二进制过滤器{#binary-filter-in-the-correlation-matrix}

{{eol}}

通过关联矩阵中的二进制过滤器，您可以限制其中一个或两个关联量度的值以更好地进行比较。

要在关联矩阵上设置二进制过滤器：

1. 从关联矩阵中，右键单击量度名称。
1. 选择&#x200B;**编辑量度详细信息**。

   ![](assets/correlation_matrix_binary_filter.png)

   的 **[!UICONTROL Edit Correlation Metric Details]** 窗口。

   ![](assets/correlation_matrix_metric_details.png)

1. 设置二进制过滤器。

   首先，单击 **[!UICONTROL Inactive]** 设置。 它将切换为 **[!UICONTROL Active]** 并显示 **比较** 和 **值** 字段。

   然后，选择 **[!UICONTROL Comparison]** 运算符和设置 **[!UICONTROL Value]** 为所选量度设置过滤器。

>[!IMPORTANT]
>
>Data Workbench6.2的二进制过滤器已更新新增功能，需要您使用在以前版本中构建的二进制过滤器重建任何关联矩阵。

## 添加维度元素 {#section-f19f4e0368ca488e92d1e28bcc24417c}

您也可以添加维度元素以约束量度。一个量度只能有一个与之相关联的元素。

![](assets/correlation_matrix_element.png)

在工作区中右键单击并选择&#x200B;**表格**。打开一个包含其元素的维度，然后拖动到 **[!UICONTROL Element]** 在“编辑关联量度详细信息”窗口中进行设置，或将量度拖放到关联矩阵中。
