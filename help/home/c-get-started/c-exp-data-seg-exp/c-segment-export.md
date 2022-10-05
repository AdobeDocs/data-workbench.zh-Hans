---
description: 为您的区段导出文件创建自定义列导出标题，以便为导出的区段添加易于理解的说明。此导出功能还允许您输出 TSV 和 CSV 文件。
title: 带有自定义标题的区段导出
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
exl-id: 1d27f926-35e1-4886-b7a6-702d9947dabb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 59%

---

# 带有自定义标题的区段导出{#segment-export-with-custom-headers}

{{eol}}

为您的区段导出文件创建自定义列导出标题，以便为导出的区段添加易于理解的说明。此导出功能还允许您输出 TSV 和 CSV 文件。

已为区段导出添加新的功能，包括带有标题的导出，或以 CSV 和 TSV 格式导出。

您可以为导出文件创建列标题。

## 创建新的区段导出 {#section-cffff55855f8467ea468b71393ab7676}

1. 打开工作区并右键单击 **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. 右键单击并选择 **[!UICONTROL Add Level > Extended]** >选择项目。
1. 右键单击标题并选择 **[!UICONTROL Add Attribute.]** 从菜单中选择一个维度。

1. 右键单击标题并选择 **[!UICONTROL Add Metric.]** 从菜单中选择一个量度。

1. 右键单击标题并选择 **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** 自动使用量度名称填充列名称。 **[!UICONTROL New Segment Export]** 需要您设置自定义名称。 ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >列名称字段不能留空或标题不存在。

1. 右键单击并命名区段，然后单击 **[!UICONTROL Save Export File]**.

   此时将打开一个导出窗口。

1. 右键单击导出名称，然后单击 **另存为`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. 右键单击 [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. 找到刚刚创建的导出文件，并将其保存到现有的配置文件中。

   ![](assets/segment_export_headers_8.png)
