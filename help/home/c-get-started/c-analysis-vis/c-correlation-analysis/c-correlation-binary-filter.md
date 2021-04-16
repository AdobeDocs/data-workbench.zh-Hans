---
description: 通过关联矩阵中的二进制过滤器，您可以限制其中一个或两个关联量度的值以更好地进行比较。
title: 关联矩阵中的二进制过滤器
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 55%

---

# 关联矩阵中的二进制过滤器{#binary-filter-in-the-correlation-matrix}

通过关联矩阵中的二进制过滤器，您可以限制其中一个或两个关联量度的值以更好地进行比较。

要在关联矩阵上设置二进制过滤器：

1. 从关联矩阵中，右键单击量度名称。
1. 选择&#x200B;**编辑量度详细信息**。

   ![](assets/correlation_matrix_binary_filter.png)

   将打开&#x200B;**[!UICONTROL Edit Correlation Metric Details]**&#x200B;窗口。

   ![](assets/correlation_matrix_metric_details.png)

1. 设置二进制过滤器。

   首先，单击&#x200B;**[!UICONTROL Inactive]**&#x200B;设置。 它将切换以将过滤器设置为&#x200B;**[!UICONTROL Active]**&#x200B;并显示&#x200B;**Comparison**&#x200B;和&#x200B;**Value**&#x200B;字段。

   然后，选择&#x200B;**[!UICONTROL Comparison]**&#x200B;运算符并设置其&#x200B;**[!UICONTROL Value]**&#x200B;以设置所选量度的过滤器。

>[!IMPORTANT]
>
>Data Workbench 6.2的二进制过滤器已使用新功能进行更新，要求您使用先前版本中构建的二进制过滤器重新构建任何相关矩阵。

## 添加维度元素 {#section-f19f4e0368ca488e92d1e28bcc24417c}

您也可以添加维度元素以约束量度。一个量度只能有一个与之相关联的元素。

![](assets/correlation_matrix_element.png)

在工作区中右键单击并选择&#x200B;**表格**。打开包含其元素的维度，并拖动到“编辑关联量度详细信息”窗口中的&#x200B;**[!UICONTROL Element]**&#x200B;设置，或放置到关联矩阵中的量度。
