---
description: 通过关联矩阵中的二进制过滤器，您可以限制其中一个或两个关联量度的值以更好地进行比较。
solution: Analytics
title: 关联矩阵中的二进制过滤器
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 关联矩阵中的二进制过滤器{#binary-filter-in-the-correlation-matrix}

通过关联矩阵中的二进制过滤器，您可以限制其中一个或两个关联量度的值以更好地进行比较。

要在关联矩阵上设置二进制过滤器：

1. 从关联矩阵中，右键单击量度名称。
1. 选择&#x200B;**编辑量度详细信息**。

   ![](assets/correlation_matrix_binary_filter.png)

   窗 **[!UICONTROL Edit Correlation Metric Details]** 口将打开。

   ![](assets/correlation_matrix_metric_details.png)

1. 设置二进制过滤器。

   First, click the **[!UICONTROL Inactive]** setting. It will toggle to set the filter as **[!UICONTROL Active]** and display the **Comparison** and **Value** fields.

   Then, select a **[!UICONTROL Comparison]** operator and set its **[!UICONTROL Value]** to set up a filter for the selected metric.

>[!IMPORTANT]
>
>Data Workbench 6.2的二进制过滤器已更新为新增功能，要求您使用先前版本中构建的二进制过滤器重新构建任何关联矩阵。

## 添加维度元素 {#section-f19f4e0368ca488e92d1e28bcc24417c}

您也可以添加维度元素以约束量度。一个量度只能有一个与之相关联的元素。

![](assets/correlation_matrix_element.png)

在工作区中右键单击并选择&#x200B;**表格**。Open a dimension with its elements and drag to the **[!UICONTROL Element]** setting in the Edit Correlation Metric Details window, or drop on a metric in the Correlation Matrix.
